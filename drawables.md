# Drawables
- If you’re assigning Drawable programmatically to multiple views and you’re modifying it’s properties - make sure to create each drawable with separate state:
```
val stateListDrawable = typedArray.getDrawable(R.styleable...)
view.setBackground(stateListDrawable.constantState
									.newDrawable()
									.mutate())
```
