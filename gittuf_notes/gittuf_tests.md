# Understanding the Gittuf codebase

## Creating a new `repo`
```
tempDir := t.TempDir()
repo := gitinterface.CreateTestGitRepository(t, tempDir, false)
```
Also check out `policy.helpers_test.createTestRepository`