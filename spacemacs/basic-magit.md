# Basic Magit operations

Basic steps of using magit (~> 2.0). All of these steps are executed from within magit status window, with exception the initial step of opening git status window.

### Getting git status

```
  <SPC> g s
```

### Updating / Refreshing git status window

On git status window itself.

```
  gr 
```

### Staging / unstaging file

Put cursor on the line that contain the target file.

To stage:
```
  s
```

To unstage:
```
  u
```

### Committing files

From git status window, start commit action:
```
  c
```

Then git commit popup window will open:
```
  c
```

Then commit window message will open; type in the commit comment and save them.

### Pull / Push git remote

Fetch from origin
```
  f u
```

Pull from origin
```
  F u
```

Push to origin
```
  P p
```

## References

* http://magit.vc/manual/magit

