## Encounter Problem

###### May-2022

1. Sometimes design will specific style for information pages with inline css in editor itself. If the information page performance is different between live and staging. Try to review the page content.
2. xlink:href is depracated
   For SVG reference, xlink:href got depreciated and is replaced with href

   ```html
   <!-- This is old -->
   <svg>
   	<use xlink:href="#id" />
   </svg>

   <!-- This is new -->
   <svg>
   	<use href="#id" />
   </svg>
   ```
3. Sticky position is not working?
   Use below link to check the root cause, commonly it is because of the overflow property set for parent/ancestor elements.

   [Ref Link](https://www.designcise.com/web/tutorial/how-to-fix-issues-with-css-position-sticky-not-working)
4. Image blurred
   Solution to keep image sharp

   * Use 2x size image
   * Configure the image width to even number.
   * Add CSS property image-rendering

    [Ref Link](https://bootcamp.uxdesign.cc/what-to-look-for-when-fixing-blurry-images-at-2x-eee36fbf0698)

