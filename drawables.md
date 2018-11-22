---


---

<h1 id="drawables">Drawables</h1>
<ul>
<li>If you’re assigning Drawable programmatically to multiple views and you’re modifying it’s properties - make sure to create each drawable with separate state:</li>
</ul>
<pre><code>val stateListDrawable = typedArray.getDrawable(R.styleable...)
view.setBackground(stateListDrawable.constantState
									.newDrawable()
									.mutate())
</code></pre>

