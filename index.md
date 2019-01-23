---
layout: default
---

# Android tips and tricks
## Drawables
###  Reusing drawables
If you’re assigning Drawable programmatically to multiple views and you’re modifying it’s properties - make sure to create each drawable with separate state:  
```
val stateListDrawable = typedArray.getDrawable(R.drawable.stateListDrawable)
view.setBackground(stateListDrawable.constantState.newDrawable().mutate())
```  
More info on that [here](http://www.curious-creature.com/2009/05/02/drawable-mutations/comment-page-1/)

## Kotlin

### Refactoring Dagger injected values
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
```
(\@Inject\n.*)(var.+?(?=\? = null))(\? = null)`
```
and this to the second:
```
$1lateinit $2
```
And hit replace all.