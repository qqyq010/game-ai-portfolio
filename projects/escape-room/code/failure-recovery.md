# 실패 처리 중 잠근 입력을 돌려주는 코드

개인 프로젝트 EscapeRoom의 2026년 3월 소스에서 가져온 코드입니다. 실패 이유에 맞는 설정을 읽어 입력을 잠근 뒤 복구를 처리합니다. 입력 잠금은 `finally`에서 풀어 줍니다. 씬에 입력 잠금 제어기가 없으면 게임 상태를 바꿔 움직임을 막았다가 다시 돌려놓습니다.

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

이 코드는 Unity 씬의 인스펙터에서 정한 복구 설정을 사용합니다. 시작 씬에서는 적에게 들키거나 보물 구간에서 실패하면 체크포인트로 돌아갑니다. 일반 퍼즐을 틀렸을 때는 그 자리에서 다시 조작할 수 있습니다. 3월 시연 영상과는 별도로 8월 자동 검사에서 대표 퍼즐을 틀린 뒤 입력이 풀리는지 확인했습니다.

- [실패 후 이어 하기 사례](../failure-and-retry.md)
- [자동 검사에서 확인한 범위](../evidence/play-mode-checks.md)
