---
title: visibility
slug: Web/SVG/Attribute/visibility
tags:
  - SVG
  - SVG Attribute
browser-compat: svg.attributes.presentation.visibility
---
{{SVGRef}}

The **`visibility`** attribute lets you control the visibility of graphical elements. With a value of `hidden` or `collapse` the current graphics element is invisible.

> **Note:** If the `visibility` attribute is set to `hidden` on a text element, then the text is invisible but still takes up space in text layout calculations.

Depending on the value of attribute {{SVGAttr("pointer-events")}}, graphics elements which have their `visibility` attribute set to `hidden` still might receive events.

> **Note:** As a presentation attribute, `visibility` can be used as a CSS property. See the {{cssxref("visibility", "CSS visibility")}} property for more information.

You can use this attribute with the following SVG elements:

- {{SVGElement("a")}}
- {{SVGElement("altGlyph")}}
- {{SVGElement("audio")}}
- {{SVGElement("canvas")}}
- {{SVGElement("circle")}}
- {{SVGElement("ellipse")}}
- {{SVGElement("foreignObject")}}
- {{SVGElement("iframe")}}
- {{SVGElement("image")}}
- {{SVGElement("line")}}
- {{SVGElement("path")}}
- {{SVGElement("polygon")}}
- {{SVGElement("polyline")}}
- {{SVGElement("rect")}}
- {{SVGElement("text")}}
- {{SVGElement("textPath")}}
- {{SVGElement("tref")}}
- {{SVGElement("tspan")}}
- {{SVGElement("video")}}

## Example

```css hidden
html, body, svg {
  height: 100%;
}
```

```html
<svg viewBox="0 0 220 120" xmlns="http://www.w3.org/2000/svg">
  <rect x="10" y="10" width="200" height="100" stroke="black"
      stroke-width="5" fill="transparent" />
  <g stroke="seagreen" stroke-width="5" fill="skyblue">
    <rect x="20" y="20" width="80" height="80" visibility="visible" />
    <rect x="120" y="20" width="80" height="80" visibility="hidden"/>
  </g>
</svg>
```

{{EmbedLiveSample("Example", "250", "100")}}

## Usage notes

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Value</th>
      <td>
        <code>visible</code> | <code>hidden</code> | <code>collapse</code>
      </td>
    </tr>
    <tr>
      <th scope="row">Default value</th>
      <td><code>visible</code></td>
    </tr>
    <tr>
      <th scope="row">Animatable</th>
      <td>Yes</td>
    </tr>
  </tbody>
</table>

- `visible`
  - : This value indicates that the element will be painted.
- `hidden`
  - : This value indicates that the element will not be painted. Though it is still part of the rendering tree, i.e. it may receive pointer events depending on the {{SVGAttr("pointer-events")}} attribute, may receive focus depending on the {{SVGAttr("tabindex")}} attribute, contributes to bounding box calculations and clipping paths, and does affect text layout.
- `collapse`
  - : This value is equal to `hidden`.

## Example

The following example toggles the CSS `visibility` of the SVG image path.

### HTML

```html
<button id="nav-toggle-button" >
  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" class="button-icon">
    <path d="M16.59 8.59L12 13.17 7.41 8.59 6 10l6 6 6-6z" />
    <path d="M12 8l-6 6 1.41 1.41L12 10.83l4.59 4.58L18 14z" class="invisible" />
    <path d="M0 0h24v24H0z" fill="none" />
  </svg>
  <span>
    click me
  </span>
</button>
```

### CSS

```css
svg {
  display: inline !important;
}
span {
  vertical-align: 50%;
}
button {
  line-height: 1em;
}
.invisible {
  visibility: hidden;
}
```

### JavaScript

```js
document.querySelector("button").addEventListener("click", function (evt) {
  this.querySelector("svg > path:nth-of-type(1)").classList.toggle("invisible");
  this.querySelector("svg > path:nth-of-type(2)").classList.toggle("invisible");
});
```

{{EmbedLiveSample("Example", "100%", "80")}}

## Specifications

<table class="no-markdown">
  <thead>
    <tr>
      <th scope="col">Specification</th>
      <th scope="col">Status</th>
      <th scope="col">Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        {{SpecName("CSS2.1", "visufx.html#visibility", "visibility")}}
      </td>
      <td>{{Spec2("CSS2.1")}}</td>
      <td>CSS definition of the property</td>
    </tr>
    <tr>
      <td>
        {{SpecName("SVG2", "render.html#VisibilityControl", "visibility")}}
      </td>
      <td>{{Spec2("SVG2")}}</td>
      <td>Mainly refers to CSS 2.1</td>
    </tr>
    <tr>
      <td>
        {{SpecName("SVG1.1", "painting.html#VisibilityProperty", "visibility")}}
      </td>
      <td>{{Spec2("SVG1.1")}}</td>
      <td>Initial definition</td>
    </tr>
  </tbody>
</table>

## Browser compatibility

{{Compat}}

## See also

- {{SVGAttr("display")}} attribute
- {{cssxref("visibility", "CSS visibility")}}
