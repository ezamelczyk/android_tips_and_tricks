---
layout: default
---

# Drawables
- If you’re assigning Drawable programmatically to multiple views and you’re modifying it’s properties - make sure to create each drawable with separate state:  
    ```
    val stateListDrawable = typedArray.getDrawable(R.styleable...)
    view.setBackground(stateListDrawable.constantState
									.newDrawable()
									.mutate())
    ```  
    More info on that [here](http://www.curious-creature.com/2009/05/02/drawable-mutations/comment-page-1/)
