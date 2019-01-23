---
layout: default
---

# Kotlin

Ever had trouble with refactoring kotlin with Dagger?  
Now you can use this simple regex to refactor this:  
```
@Inject 
var injected: Sometype? = null  
```
to this:
```
@Inject
lateinit var injected: Sometype
```

Just hit `cmd+R` and paste this simple regex into the first field:

`(\@Inject\n.*)(var.+?(?=\? = null))(\? = null)`

and this to the second:

`$1lateinit $2`

And hit replace all.