# 실패 처리 중 잠근 입력을 돌려주는 코드

개인 프로젝트 EscapeRoom의 2026년 3월 소스에서 실패 처리 메서드를 발췌했습니다. 실패 이유에 맞는 복구 설정을 읽고 입력을 잠급니다. 복구 처리와 별도로 `finally`에서 입력 잠금을 풀어 줍니다. 잠금 제어기가 없는 씬에서는 게임 상태를 통해 조작을 제한하고 복귀시킵니다.

```csharp
private IEnumerator HandleFailureRoutine(FailureReason reason, Transform source)
{
    // 실패 원인별 동작을 하드코딩하지 않고 inspector 데이터에서 가져온다.
    FailureRecoveryProfile profile = GetRecoveryProfile(reason);

    int lockToken = -1;
    _isHandlingFailure = true;
    try
    {
        if (_inputLockController != null)
            lockToken = _inputLockController.LockInput(profile.RestoreState, reason.ToString());
        else
            GameManager.Instance?.SetState(GameState.Locked);


        if (profile.Delay > 0f)
            yield return new WaitForSeconds(profile.Delay);

        // 복구 처리와 입력 복구를 분리해 두면 나중에 한쪽만 독립적으로 확장하기 쉽다.
        ApplyRecovery(profile);
    }
    finally
    {
        if (_inputLockController != null)
            _inputLockController.UnlockInput(lockToken);
        else
            GameManager.Instance?.SetState(profile.RestoreState);

        _isHandlingFailure = false;
    }
}
```

이 메서드를 실행하려면 Unity 씬의 인스펙터 설정과 프로젝트의 입력 제어기가 필요합니다. 시작 씬에는 감지와 보물 실패를 체크포인트 복귀로, 일반 퍼즐 실패를 입력만 반환하는 흐름으로 설정했습니다. 당시 영상, C# 소스 발췌, 8월의 별도 자동 검사는 서로 다른 근거입니다. [실패 후 이어 하기 사례](../failure-and-retry.md) · [자동 검사에서 확인한 범위](../evidence/play-mode-checks.md)
