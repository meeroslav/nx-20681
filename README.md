# Nx20681

Original issue: https://github.com/nrwl/nx/issues/20681

## Scenario 1
To reproduce:
- yarn --immutable
- yarn nx migrate latest
- yarn
- yarn nx migrate --run-migrations

This should error with:
```
Error: nx tried to access v8-compile-cache, but it's not declared in its declarations; this makes the require call ambiguous and unsound.
```

## Scenario 2
To reproduce:
- yarn add -D v8-compile-cache@2.3.0
- yarn --immutable
- yarn nx migrate latest
- yarn
- yarn nx migrate --run-migrations

This should error with:
```
Failed to run 17.0.0-move-cache-directory from nx. This workspace is NOT up to date.
```
