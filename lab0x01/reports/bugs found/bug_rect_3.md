# BUG-RECT-3
## Category
Unchecked system call returning code

## Description
The `store_png` function is called but the return value is not checked.

## Affected Lines in the original program
`rect.c:85`

## Expected vs Observed
The resulting image should have been stored correctly but this is not the case as the `store_png` function failed. The program should have exit with a return code indicating an error but this is also not the case.

## Steps to Reproduce

### Command
```
./rect test.png /inexistant/folder/test_rect.png 100 100 200 50 FFFFFFF
```

### Proof-of-Concept Input (if needed)

## Suggested Fix Description
The return value should be checked and if the function has failed, we should print an error message and return an error code.