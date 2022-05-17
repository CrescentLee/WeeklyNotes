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
5. Youtube auto play on mobile?
   Currently iframe videos cannot perform autoplay on mobile. The various reasons include data usage, spam ads, etc.
6. Error Diagnose: 500 Internal Server Error occurs when submit a request with huge text body
   Issue: The problem happened on local only. When submit a request with large request body (e.g. chunck HTML code), request will be terminated with 500 Internal Server Error poped out.
   Local server is running with Nginx, check Nginx error log found the error code is like this:

   ```
   nginx/client_body_temp/0000000007" failed (13: Permission denied)
   ```

   After investigation, found that the default request body size of Nginx is `client_body_buffer_size 8k|16k` (8K on x86,other platforms, x86-64 and 16K on 64-bit platforms). If the request body size is smaller than 8K, then data will be proceeded to RAM, if the request body size is larger than 8K, then data will be proceeded to a temporary file.
   Therefore in this case, when the html content is larger than the buffer size, it will write to the temporary file. Moreover, by default the folder `nginx/client_body_temp` is set prehibited to access. So when server would like to access the HTML content stored in the temporary folder, error is triggered.
   [Ref Link 1](https://n8williams.com/devblog/mac-development/nginx-client_body_temp-failed-13-permission-denied-error)
   [Ref Link 2](https://serverfault.com/questions/875019/optimizing-nginx-client-body-buffer-size-for-web-app-accepting-file-uploads)

7.

