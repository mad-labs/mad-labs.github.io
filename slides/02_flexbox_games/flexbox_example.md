
### Example

With this html:

```html
<!DOCTYPE html>
<html>
  <body>
    <div class="fl-sb-v">
      <div class="fl-sb-h c-st">
        <div class="fl-ct">
          <div class="fl-ct i-st">1</div>
          <div class="fl-ct i-st">2</div>
          <div class="fl-ct i-st">3</div>
        </div>
        <div class="fl-ct">
          <div class="fl-ct i-st">4</div>
          <div class="fl-ct i-st">5</div>
        </div>
      </div>
      <div class="fl-ct">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
      </div>
      <div class="fl-sb-h c-st">
        <div class="fl-ct i-st">6</div>
        <div class="fl-ct i-st">7</div>
      </div>
    </div>
  </body>
</html>
```

<!-- next-slide -->

how it takes to have this layout with standard css?

![Example]({{ "assets/images/example_flexbox.png" }})

<!-- next-slide -->

Here there is the css with flexbox model:

```css
.fl-sb-v {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
.fl-sb-h {
    display: flex;
    justify-content: space-between;
}
.fl-ct {
    display: flex;
    justify-content: center;
    align-items: center;
}
[...]
```

<!-- next-slide -->

### Holy Grail Layout example

This example demonstrates how flexbox provides the ability to dynamically change the layout for different screen resolutions.

![Example]({{ "assets/images/example.png" }})

[https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes#Holy_Grail_Layout_example](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes#Holy_Grail_Layout_example)

<!-- next-slide -->