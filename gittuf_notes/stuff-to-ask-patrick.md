# Stuff to ask Patrick 

## Gittuf codebase
1. Explain `context.Backround()` please
2. Explain `TestLoadFirstState` - why would the first state and latest state be the same?
3. In `policy`, although in `state := createTestStateWithDelegatedPolicies(t)`, we initialize `s.DelegationEnvelopes`, it shows that it isn't getting tested. Why? 
4. How is the same pub key being used for enc and non enc keys? (in ssh tests)
5. `policy.go` line 222, did not understand what the comment means
6. What is a verifier?
7. in `CommitUsingSpecificKey()` why aren't we doing the same thing as the `Commit()` function? As in using the `r.executor()` method?

## Windows
1. Discuss the keys thing (same public key for two different private keys)
2. Discuss the difference in length of signatures

## Status update
1. Increased `policy.go` test coverage from 72% to 79.7%. The remaining stuff is error catching.
2. 