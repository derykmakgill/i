
<h1><a id="user-content-how-to-build-a-low-tech-website-design-techniques-and-process" class="anchor" href="#how-to-build-a-low-tech-website-design-techniques-and-process" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>How to Build a Low-tech Website: Design Techniques and Process</h1>
<p>Low-tech Magazine is a technology website that looks at sustainable historical alternatives to modern-day tech. A radical redesign, intended to minimize the energy used to access its content, recently launched at <a href="https://solar.lowtechmagazine.com/" rel="nofollow">solar.lowtechmagazine.com</a>.</p>
<p>This article / wiki focuses on the front-end efforts involved in this project, and is a compendium to <a href="https://solar.lowtechmagazine.com/2018/09/how-to-build-a-lowtech-website.html" rel="nofollow">How to Build a Low-tech Website</a>, which summarizes our primary design decisions and motivations, and <a href="https://homebrewserver.club/low-tech-website-howto.html" rel="nofollow">How to build a Low-Tech website: Software &amp; Hardware</a>, which documents the back-end technical details. It's written as an introductory text for those with basic knowledge of front-end languages (HTML, CSS, JS.)</p>
<p>Part 1 reviews some specific techniques used in the design. Part 2 (to come) delves into the process of static site generation and development, and how that fits into the larger ecosystem of the internet.</p>
<p>Some background: the website is a static site generated with <a href="http://docs.getpelican.com/en/stable/" rel="nofollow">Pelican</a>, and the theme stylesheets were developed using <a href="https://sass-lang.com/" rel="nofollow">SCSS</a>.</p>
<h1>
<a id="user-content-part-1-design" class="anchor" href="#part-1-design" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Part 1: Design</h1>
<p>A core part of the design process was to interrogate which design elements and features can be sacrificed and which are absolutely necessary for the site's purposes. What kind of changes in user experience can question our relationship to the internet, while still being functional?</p>
<p>In considering internet sustainability, the design of a website constitutes the majority of energy use. "[F]rontend components—JavaScript, images, CSS/ HTML, and other assets, plus page rendering tasks a browser must perform—comprised between 76 to 92% of total page load time. Because design decisions drive so much of what happens on the frontend, designers clearly have a critical role to play in creating optimized solutions." (Tim Frick, <em>Designing for Sustainability</em>.) Considering this, our design approach was to prioritize using the least amount of resources to enable a website that can be powered from a small-scale solar panel.</p>
<h2>
<a id="user-content-logo" class="anchor" href="#logo" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Logo</h2>
<p>Low-tech’s mission is to look to technologies of past for inspiration for our future. In keeping with their approach, we decided on a simple typographic move instead of a logo: a left-facing arrow as the hyphen. LOW←TECH MAGAZINE, in all forms it takes across platforms, is our identity. The arrow also draws from Low-tech’s previous image masthead of a spear, as a low-tech weapon against prevailing the claims of high-tech progress.</p>
<p>Specifically, it uses the unicode: <code>&amp;larr;</code> or <code>U+02190</code>, which, if not included in the default typeface, will use any symbol font available to the user to render it.</p>
<p>As some have noted, it’s possible to embed inline SVGs with minimal overhead on websites, since SVGs are a scalable and lightweight image format. But once a logotype is set in vector form, it needs to be distributed accordingly. Logos are now required for any form of representation, often involving a zipped package with eps, ai, png, and jpeg files all in order to ensure that the end-user has a program to use at least one of them. (If you think about it, using a letter / symbol is the equivalent of inline SVGs in print form...)</p>
<p>This approach avoids the need to distribute these assets but also strengthens the identity as a versatile, medium-specific voice. The identity calls for conceptual consistency over visual uniformity.</p>
<h2>
<a id="user-content-default-typeface" class="anchor" href="#default-typeface" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Default typeface</h2>
<p>In the early decades of the web, we only saw system fonts used on the web. System fonts such as Arial, Times New Roman, Georgia, and Verdana were most likely to be available on all operating systems, whether Windows / Mac or other. This ensured that the website will more or less look consistent for the majority of users.</p>
<p>Now, with the <code>@font-face</code> rule and webfont distributors, it's extremely easy to embed a typeface within a website. But they come at a cost: custom fonts impact performance, often adding several seconds of load time to a page. Several strategies by name of <a href="https://css-tricks.com/fout-foit-foft/" rel="nofollow">FOUT, FOIT, or FOFT</a> are options to address this issue. (An unintentional side effect was also that it led to enabling mass piracy of typefaces.)</p>
<p>But with customized typefaces all over the web, it's often easy to overlook the fact that even before the website's CSS kicks in, the "user-agent" stylesheet, or your browser settings, applies styles to the website. One of the first things we learn as front-end designers is that all the website-specific styling we see is simply overriding these browser defaults.</p>
<p>This design leverages these defaults, as it does not declare a <code>font-family</code> at all. This not only avoids having to load more assets, but also reiterates the role of the browser in website access. Moreover, only one weight (regular) of a font is used, demonstrating that typographic hierarchy that can be established without loading multiple typefaces and weights.</p>
<p>The lack of a <code>font-family</code> declaration also empowers the user to customize the look / feel to their own choosing: if users dislike the typeface displayed on the site, they can go into their browser settings to change this. Below are screenshots of this process in commonly used browsers.</p>
<h4>
<a id="user-content-firefox" class="anchor" href="#firefox" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Firefox</h4>
<p>Go to Preferences, and in General, scroll to Language and Appearance to see Fonts &amp; Colors  <code>about:preferences</code></p>
<p><img src="https://camo.githubusercontent.com/022b17f99eee303fc517097c530f72a7482e0e59/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f66697265666f782e706e67" alt="firefox" data-canonical-src="https://marieotsuka.github.io/blog/img/firefox.png"></p>
<h4>
<a id="user-content-chrome" class="anchor" href="#chrome" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Chrome</h4>
<p>Go to Settings, and scroll down to Appearance, then select Customize Fonts <code>chrome://settings/fonts</code></p>
<p><img src="https://camo.githubusercontent.com/5570208b7c47d18845fe063420983a593f5e3140/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f6368726f6d652e706e67" alt="chrome" data-canonical-src="https://marieotsuka.github.io/blog/img/chrome.png"></p>
<h4>
<a id="user-content-safari" class="anchor" href="#safari" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Safari</h4>
<p>It looks like newer version of Safari have removed the font customization feature, which used to be in the Appearance tab of Preferences. The latest version barely has any out-of-the box controls, although it looks like it allows you to use your own stylesheet if you know CSS.</p>
<p><img src="https://camo.githubusercontent.com/5f20b9dcce34c6524241f5695d37bb95777a5017/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f7361666172692e706e67" alt="safari" data-canonical-src="https://marieotsuka.github.io/blog/img/safari.png"></p>
<h2>
<a id="user-content-images" class="anchor" href="#images" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Images</h2>
<p>The lightest websites would exist without any images or graphical elements. That said, imagery is an important part of communicating content. We used several techniques to minimize the server and data load for our images: heavily compressed dithered images, inline SVGs, and image sprites.</p>
<h3>
<a id="user-content-dithered-images" class="anchor" href="#dithered-images" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Dithered images</h3>
<p>Instead of using full-color high-resolution images, we chose to convert all images to black and white, with 4 levels of gray in-between via a custom <a href="https://homebrewserver.club/low-tech-website-howto.html#image-compression" rel="nofollow">dithering plugin</a>.</p>
<p>As several readers have noted, certain images are better suited for other forms of compression. But our goal was to not only compress images, but also to call to attention this act of compression. And considering that the majority of articles feature archival black and white imagery, compressing into a file format with indexed color (in which the number of colors determines its weight) was most appropriate for the limited color palette.</p>
<p>Moreover, we found that dithered images can be stretched beyond their actual image size to emphasize its distinct aesthetic, and that these artifacts of compression can become an integral part of the design.</p>
<p>It's common practice today to generate multiple sizes of the same image in order to display the appropriate size for the platform (desktop, tablet, mobile.) Here, however, we opted to use the same image file for both thumbnail and featured images to prioritize the browser's cache of the loaded image, even if it means that the initial listing pages may be a bit heavier.</p>
<p>These black and white images are then colored according to the pertaining content category (Low-tech Solution, High-tech Problems, or Obsolete Technology) via <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode" rel="nofollow">CSS blend-modes</a>. The <code>hard-light</code> overlay technique allows only the white parts of the image against its background, allowing the color behind the image to colorize it.</p>
<p>For background images, we can use the <code>background-color</code>. For content images in articles, we will need it in a wrapper (coloring the <code>img</code> background does not work.) Fortunately, the format in which the articles are written – in markdown — automatically wraps images specfied in a paragraph tag. These image-wrapping paragraphs were captured via the <a href="https://github.com/lowtechmag/solar-plugins/tree/master/addressable_paragraphs">addressable a Pelican plugin</a> in order to colorize the images.</p>
<p>Original image <img src="https://camo.githubusercontent.com/60fafb5f827374ecb37b77c7ed13b23188202b5e/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f73746f6e6566657272792d64657461696c2e706e67" alt="original image" data-canonical-src="https://marieotsuka.github.io/blog/img/stoneferry-detail.png"></p>
<p>Compressed image <img src="https://camo.githubusercontent.com/8d9fc2e52c1e4e7fb9a85f478dbb5c984492ca85/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f62772e706e67" alt="black and white" data-canonical-src="https://marieotsuka.github.io/blog/img/bw.png"></p>
<p>Colorized image <img src="https://camo.githubusercontent.com/667d11f2177d859dfe0d4cf7571f6d77e9e4dfc6/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f636f6c6f7265642e706e67" alt="colorized" data-canonical-src="https://marieotsuka.github.io/blog/img/colored.png"></p>
<p>For thumbnail images on an article listings page:</p>
<p>CSS</p>
<div class="highlight highlight-source-css"><pre><span class="pl-e">.featured-img</span> {
	<span class="pl-c1"><span class="pl-c1">background-blend-mode</span></span>: <span class="pl-c1">hard-light</span>;
}
</pre></div>
<p>HTML</p>
<div class="highlight highlight-text-html-basic"><pre>&lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>featured-img<span class="pl-pds">"</span></span> <span class="pl-e">style</span>=<span class="pl-s"><span class="pl-pds">"</span><span class="pl-s1"><span class="pl-c1"><span class="pl-c1">background-image</span></span>: <span class="pl-c1">url</span>(<span class="pl-s"><span class="pl-pds">'</span>path/to/image<span class="pl-pds">'</span></span>)</span><span class="pl-pds">"</span></span>&gt;&lt;/<span class="pl-ent">div</span>&gt;</pre></div>
<p>For images in an article:</p>
<p>CSS</p>
<div class="highlight highlight-source-css"><pre><span class="pl-ent">p</span><span class="pl-e">.img</span> {
	<span class="pl-c1"><span class="pl-c1">background-color</span></span>: $color_low;
}

<span class="pl-ent">img</span> {
	<span class="pl-c1"><span class="pl-c1">mix-blend-mode</span></span>: <span class="pl-c1">hard-light</span>;
}</pre></div>
<p>HTML</p>
<div class="highlight highlight-text-html-basic"><pre>&lt;<span class="pl-ent">p</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>img<span class="pl-pds">"</span></span>&gt;&lt;<span class="pl-ent">img</span> <span class="pl-e">alt</span>=<span class="pl-s"><span class="pl-pds">"</span>image alt tag<span class="pl-pds">"</span></span> <span class="pl-e">src</span>=<span class="pl-s"><span class="pl-pds">"</span>path/to/image<span class="pl-pds">"</span></span>/&gt;&lt;/<span class="pl-ent">p</span>&gt;</pre></div>
<h3>
<a id="user-content-svg" class="anchor" href="#svg" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>SVG</h3>
<p>SVGs can be used either as an image file (<code>externalfile.svg</code>) or pasted into the html file as inline code (<code>&lt;svg&gt;&lt;/svg&gt;</code>). Any application capable of producing vector drawings should be able to export in SVG format, and simply opening the file in a text editor reveals its code. Inline SVGs allow us to prevent load requests for images. While there may be advantages to caching loaded images, inline SVGs also have another benefit: they can be styled with css classes. Thus, any icon that would require hover states are in inline SVG format. (One note: because SVGs are essentially images, the syntax for SVGS differs from styling HTML elements. Read more on <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial" rel="nofollow">SVGs at MDN</a>.)</p>
<p>Inline SVG</p>
<div class="highlight highlight-text-html-basic"><pre>&lt;<span class="pl-ent">a</span> <span class="pl-e">href</span>=<span class="pl-s"><span class="pl-pds">"</span>https://solar.lowtechmagazine.com/power.html<span class="pl-pds">"</span></span>&gt;This is a solar-powered website, which means it sometimes goes offline 
	&lt;svg class="icon" viewBox="0 0 500 500"&gt;&lt;title&gt;Solar&lt;/title&gt;&lt;circle class="svg_fill" cx="248.48" cy="252.55" r="97.03"&gt;&lt;/circle&gt;&lt;rect class="svg_fill" x="234.53" y="17.45" width="27.9" height="112.39"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="234.53" y="375.25" width="27.9" height="112.39"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="413.42" y="196.35" width="27.9" height="112.39" transform="translate(679.92 -174.83) rotate(90)"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="55.63" y="196.35" width="27.9" height="112.39" transform="translate(322.12 182.97) rotate(90)"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="361.03" y="69.85" width="27.9" height="112.39" transform="translate(198.96 -228.23) rotate(45)"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="108.03" y="322.85" width="27.9" height="112.39" transform="translate(303.75 24.77) rotate(45)"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="361.03" y="322.85" width="27.9" height="112.39" transform="translate(908.15 381.93) rotate(135)"&gt;&lt;/rect&gt;&lt;rect class="svg_fill" x="108.03" y="69.85" width="27.9" height="112.39" transform="translate(297.35 128.93) rotate(135)"&gt;&lt;/rect&gt;&lt;/svg&gt;
&lt;/<span class="pl-ent">a</span>&gt;
</pre></div>
<p>SCSS</p>
<div class="highlight highlight-source-css-scss"><pre><span class="pl-e">.svg_stroke</span>{
	<span class="pl-c1"><span class="pl-c1">fill</span></span>:<span class="pl-c1">none</span>;
	<span class="pl-c1"><span class="pl-c1">stroke</span></span>: <span class="pl-c1">black</span>;
	<span class="pl-c1"><span class="pl-c1">stroke-miterlimit</span></span>:<span class="pl-c1">10</span>;
	<span class="pl-c1"><span class="pl-c1">stroke-width</span></span>:<span class="pl-c1">33<span class="pl-k">px</span></span>;
}

<span class="pl-e">.svg_fill</span>{
	<span class="pl-c1"><span class="pl-c1">fill</span></span>: <span class="pl-c1">black</span>;
}

<span class="pl-ent">a</span><span class="pl-e">:hover</span> {
	<span class="pl-e">.svg_stroke</span>{
		<span class="pl-c1"><span class="pl-c1">stroke</span></span>: <span class="pl-c1">grey</span>;
	}
	<span class="pl-e">.svg_fill</span>{
		<span class="pl-c1"><span class="pl-c1">fill</span></span>: <span class="pl-c1">grey</span>;
	}
}</pre></div>
<h3>
<a id="user-content-image-sprites" class="anchor" href="#image-sprites" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Image sprites</h3>
<p>Another technique to minimize server requests is the use of <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Implementing_image_sprites_in_CSS" rel="nofollow">image sprites</a>, which combines multiple small images into one to minimize HTTP requests.
Storage-wise, six image files (150 x 150 each) totalled 9KB, whereas the combined image (150 x 900) is a 6KB file that only loads once.</p>
<p>JavaScript adds weather-specific CSS classes read from the existing server stats, which pulls weather information from DarkSky.net(<a href="https://darksky.net/forecast/41.3829,2.1774/us12/en" rel="nofollow">https://darksky.net/forecast/41.3829,2.1774/us12/en</a>).
The CSS file then sets up the image as a background and adjusts which part of the image to display according to the class.</p>
<div class="highlight highlight-source-js"><pre><span class="pl-k">var</span> weather_ignore <span class="pl-k">=</span> [<span class="pl-s"><span class="pl-pds">"</span>snow<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>sleet<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>wind<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>fog<span class="pl-pds">"</span></span>]; <span class="pl-c"><span class="pl-c">//</span>because Barcelona is paradise</span>
<span class="pl-k">var</span> weather_data <span class="pl-k">=</span> [<span class="pl-s"><span class="pl-pds">"</span>today<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>tomorrow<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>day_after_t<span class="pl-pds">"</span></span>];
<span class="pl-k">var</span> weather_days <span class="pl-k">=</span> [<span class="pl-s"><span class="pl-pds">"</span>today<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>tomorrow<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>day after tomorrow<span class="pl-pds">"</span></span>];
<span class="pl-k">var</span> forecast <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span><span class="pl-pds">"</span></span>;

<span class="pl-c"><span class="pl-c">//</span>build forecast string to show weather icons</span>
<span class="pl-k">for</span> (i <span class="pl-k">=</span> <span class="pl-c1">0</span>; i <span class="pl-k">&lt;</span> <span class="pl-smi">weather_data</span>.<span class="pl-c1">length</span>; i<span class="pl-k">++</span>) {
    <span class="pl-k">var</span> key <span class="pl-k">=</span> weather_data[i]; <span class="pl-c"><span class="pl-c">//</span>for each day</span>
    <span class="pl-k">var</span> icon_name <span class="pl-k">=</span> key <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">"</span>_icon<span class="pl-pds">"</span></span>; <span class="pl-c"><span class="pl-c">//</span>today_icon, etc</span>
    <span class="pl-k">var</span> text <span class="pl-k">=</span> data[key]; <span class="pl-c"><span class="pl-c">//</span>weather description</span>

    <span class="pl-k">var</span> weather_icon;
    <span class="pl-c"><span class="pl-c">//</span>use cloud icon for all overcast weather</span>
    <span class="pl-k">if</span>(<span class="pl-smi">weather_ignore</span>.<span class="pl-en">includes</span>(data[icon_name])){
      weather_icon <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>cloudy<span class="pl-pds">"</span></span>;
    }<span class="pl-k">else</span>{
      weather_icon <span class="pl-k">=</span> data[icon_name];
    }
    forecast <span class="pl-k">+=</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;span class="weather_day" id="<span class="pl-pds">'</span></span> <span class="pl-k">+</span> key <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>" title="<span class="pl-pds">'</span></span> <span class="pl-k">+</span> text <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>"&gt;<span class="pl-pds">'</span></span> <span class="pl-k">+</span> weather_days[i] <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/span&gt;&lt;span class="weather_icon <span class="pl-pds">'</span></span> <span class="pl-k">+</span> weather_icon <span class="pl-k">+</span><span class="pl-s"><span class="pl-pds">'</span>"&gt; &lt;/span&gt;&lt;span class="weather_text"&gt; <span class="pl-pds">'</span></span> <span class="pl-k">+</span> text <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/span&gt;<span class="pl-pds">'</span></span>;
}

<span class="pl-c"><span class="pl-c">//</span>add it to wherever there is class "forecast" </span>
<span class="pl-k">var</span> weatherinfo <span class="pl-k">=</span> <span class="pl-c1">document</span>.<span class="pl-c1">querySelectorAll</span>(<span class="pl-s"><span class="pl-pds">'</span>.forecast<span class="pl-pds">'</span></span>);
[].<span class="pl-smi">forEach</span>.<span class="pl-c1">call</span>(weatherinfo, <span class="pl-k">function</span>(<span class="pl-smi">target</span>) {
    <span class="pl-smi">target</span>.<span class="pl-smi">innerHTML</span> <span class="pl-k">=</span> forecast;
});</pre></div>
<p><img src="https://camo.githubusercontent.com/da8a72f9970b8068b278ba1402dd43259d555e82/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f776561746865725f7370726974652e706e67" alt="icon sprite" data-canonical-src="https://marieotsuka.github.io/blog/img/weather_sprite.png"></p>
<div class="highlight highlight-source-css"><pre><span class="pl-e">.weather_icon</span> {
  <span class="pl-c1"><span class="pl-c1">background</span></span>: <span class="pl-c1">url</span>(<span class="pl-v">/extra/weather_sprite.png</span>);
  <span class="pl-c1"><span class="pl-c1">display</span></span>: <span class="pl-c1">inline-block</span>;
  <span class="pl-c1"><span class="pl-c1">height</span></span>: <span class="pl-c1">1<span class="pl-k">rem</span></span>;
  <span class="pl-c1"><span class="pl-c1">width</span></span>: <span class="pl-c1">1<span class="pl-k">rem</span></span>;
  <span class="pl-c1"><span class="pl-c1">position</span></span>: <span class="pl-c1">relative</span>;
  <span class="pl-c1"><span class="pl-c1">top</span></span>: <span class="pl-c1">3<span class="pl-k">px</span></span>;
  <span class="pl-c1"><span class="pl-c1">background-size</span></span>: <span class="pl-c1">120<span class="pl-k">px</span></span>;
	<span class="pl-c1"><span class="pl-c1">background-position</span></span>: <span class="pl-c1">-40<span class="pl-k">px</span></span> <span class="pl-c1">0</span>;
}

<span class="pl-e">.partly-cloudy-day</span> {
  <span class="pl-c1"><span class="pl-c1">background-position</span></span>: <span class="pl-c1">-20<span class="pl-k">px</span></span> <span class="pl-c1">0</span>;
}
<span class="pl-e">.clear-day</span> {
  <span class="pl-c1"><span class="pl-c1">background-position</span></span>: <span class="pl-c1">0</span> <span class="pl-c1">0</span>;
}
<span class="pl-e">.clear-night</span> {
  <span class="pl-c1"><span class="pl-c1">background-position</span></span>: <span class="pl-c1">-60<span class="pl-k">px</span></span> <span class="pl-c1">0</span>;
}
<span class="pl-e">.partly-cloudy-night</span> {
  <span class="pl-c1"><span class="pl-c1">background-position</span></span>: <span class="pl-c1">-80<span class="pl-k">px</span></span> <span class="pl-c1">0</span>;
}
<span class="pl-e">.rain</span> {
  <span class="pl-c1"><span class="pl-c1">background-position</span></span>: <span class="pl-c1">-100<span class="pl-k">px</span></span> <span class="pl-c1">0</span>;
}</pre></div>
<h1>
<a id="user-content-js" class="anchor" href="#js" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>JS</h1>
<p>Similar to images, any external files for script are additional requests to the server.
Instead of including robust but often excessive libraries such as jQuery, any JavaScript required was written in native JavaScript to avoid external dependencies. Scripts were also limited to the page used, so that they are only loaded whenever necessary. For example, the archive page allows users to rearrange the long listing, thanks to <a href="https://github.com/Sjeiti/TinySort">TinySort</a>, a lightweight sorting plugin.</p>
<h2>
<a id="user-content-visible-infrastructure" class="anchor" href="#visible-infrastructure" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Visible Infrastructure</h2>
<h3>
<a id="user-content-battery-meter" class="anchor" href="#battery-meter" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Battery Meter</h3>
<p>The design features a background color that indicates the capacity of the solar-charged battery for the website server. It's designed to always display the relationship of the energy powering the website and the visitor traffic consuming it. Decreasing height of the bar indicates that the remaining time that the website is up is limited.</p>
<h4>
<a id="user-content-html" class="anchor" href="#html" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>HTML</h4>
<p>The meter consists of two fixed-position elements, allowing content to overlap on top of it.
While the percentage indicator (<code>&lt;div id="bat_data&gt;"</code>)was originally part of the same background layer, it's now separated and pushed up into the foreground to be clickable.</p>
<div class="highlight highlight-text-html-basic"><pre>&lt;<span class="pl-ent">body</span>&gt;
&lt;<span class="pl-ent">div</span> <span class="pl-e">id</span>=<span class="pl-s"><span class="pl-pds">"</span>bat_data<span class="pl-pds">"</span></span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>bat_status<span class="pl-pds">"</span></span>&gt;
  &lt;<span class="pl-ent">a</span> <span class="pl-e">href</span>=<span class="pl-s"><span class="pl-pds">"</span>/power.html<span class="pl-pds">"</span></span> <span class="pl-e">title</span>=<span class="pl-s"><span class="pl-pds">"</span>Battery Capacity<span class="pl-pds">"</span></span>&gt;
    &lt;<span class="pl-ent">span</span> <span class="pl-e">id</span>=<span class="pl-s"><span class="pl-pds">"</span>charge_icon<span class="pl-pds">"</span></span>&gt;&lt;/<span class="pl-ent">span</span>&gt;
    &lt;<span class="pl-ent">span</span> <span class="pl-e">id</span>=<span class="pl-s"><span class="pl-pds">"</span>level<span class="pl-pds">"</span></span>&gt;0%&lt;/<span class="pl-ent">span</span>&gt;&lt;/<span class="pl-ent">a</span>&gt;
&lt;/<span class="pl-ent">div</span>&gt;
&lt;<span class="pl-ent">div</span> <span class="pl-e">id</span>=<span class="pl-s"><span class="pl-pds">"</span>battery<span class="pl-pds">"</span></span>&gt;
&lt;/<span class="pl-ent">div</span>&gt;
...</pre></div>
<h4>
<a id="user-content-css" class="anchor" href="#css" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>CSS</h4>
<p>SCSS</p>
<div class="highlight highlight-source-css"><pre><span class="pl-c"><span class="pl-c">/*</span></span>
<span class="pl-c">BACKGROUND and BATTERY METER</span>
<span class="pl-c"><span class="pl-c">*/</span></span>
<span class="pl-e">#battery</span> {
	<span class="pl-c1"><span class="pl-c1">position</span></span>: <span class="pl-c1">fixed</span>;
	<span class="pl-c1"><span class="pl-c1">bottom</span></span>: <span class="pl-c1">0</span>;
	<span class="pl-c1"><span class="pl-c1">left</span></span>: <span class="pl-c1">0</span>;
	<span class="pl-c1"><span class="pl-c1">width</span></span>: <span class="pl-c1">100<span class="pl-k">vw</span></span>;
	<span class="pl-c1"><span class="pl-c1">background</span></span>: $color_bg;
}

<span class="pl-e">#bat_data</span> {
	<span class="pl-c1"><span class="pl-c1">position</span></span>: <span class="pl-c1">fixed</span>;
	<span class="pl-c1"><span class="pl-c1">bottom</span></span>: <span class="pl-c1">0</span>;
	<span class="pl-c1"><span class="pl-c1">right</span></span>: <span class="pl-c1">0</span>;
	<span class="pl-c1"><span class="pl-c1">z-index</span></span>: <span class="pl-c1">100</span>;
	<span class="pl-c1"><span class="pl-c1">font-size</span></span>: <span class="pl-c1">0.75<span class="pl-k">rem</span></span>;
	<span class="pl-c1"><span class="pl-c1">text-align</span></span>: <span class="pl-c1">right</span>;
	<span class="pl-c1"><span class="pl-c1">padding</span></span>: <span class="pl-c1">3<span class="pl-k">px</span></span> <span class="pl-c1">.5<span class="pl-k">rem</span></span> <span class="pl-c1">0</span> <span class="pl-c1">0</span>;
	<span class="pl-c1"><span class="pl-c1">border-top</span></span>: <span class="pl-c1">1<span class="pl-k">px</span></span> <span class="pl-c1">solid</span> $<span class="pl-c1">color</span>;
}</pre></div>
<h4>
<a id="user-content-javascript" class="anchor" href="#javascript" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>JavaScript</h4>
<p>The JS reads in server stats that lives on a .json file. The battery capacity data is given as a percentage, which sets the height of the bar (<code>#battery</code>) and position of the indicator(<code>#bat_data</code>).</p>
<div class="highlight highlight-source-js"><pre><span class="pl-k">var</span> level <span class="pl-k">=</span> <span class="pl-smi">data</span>.<span class="pl-smi">bat_capacity</span>; <span class="pl-c"><span class="pl-c">//</span>i.e. 33%</span>
<span class="pl-c1">document</span>.<span class="pl-c1">getElementById</span>(<span class="pl-s"><span class="pl-pds">'</span>battery<span class="pl-pds">'</span></span>).<span class="pl-c1">style</span>.<span class="pl-c1">height</span> <span class="pl-k">=</span> level; <span class="pl-c"><span class="pl-c">//</span>uses battery percentage for CSS percentage units</span>
<span class="pl-c1">document</span>.<span class="pl-c1">getElementById</span>(<span class="pl-s"><span class="pl-pds">'</span>bat_data<span class="pl-pds">'</span></span>).<span class="pl-c1">style</span>.<span class="pl-c1">top</span> <span class="pl-k">=</span> <span class="pl-c1">100</span> <span class="pl-k">-</span> <span class="pl-c1">parseInt</span>(<span class="pl-smi">level</span>.<span class="pl-c1">slice</span>(<span class="pl-c1">0</span>, <span class="pl-k">-</span><span class="pl-c1">1</span>)) <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">"</span>vh<span class="pl-pds">"</span></span>;
<span class="pl-c"><span class="pl-c">//</span>converts to battery percentage to viewport height units from the top</span></pre></div>
<p>There is also some JS to indicate whether or not the meter is charging. When the website is powered directly with the solar panels (and the battery is charging,) it displays a sun icon. Otherwise, when running on battery, it displays a battery icon.</p>
<div class="highlight highlight-source-js"><pre><span class="pl-k">if</span> (<span class="pl-smi">data</span>.<span class="pl-smi">ac_power</span> <span class="pl-k">==</span> <span class="pl-s"><span class="pl-pds">"</span>0W<span class="pl-pds">"</span></span>) {
    power <span class="pl-k">=</span> <span class="pl-smi">data</span>.<span class="pl-smi">bat_power</span>;
    charge_icon <span class="pl-k">=</span> battery_icon;
} <span class="pl-k">else</span> {
    power <span class="pl-k">=</span> <span class="pl-smi">data</span>.<span class="pl-smi">ac_power</span>;
    charge_icon <span class="pl-k">=</span> solar_icon;
    bat_text <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>charging battery<span class="pl-pds">"</span></span>;
}</pre></div>
<p>The icons are stored as inline SVGs and written into the page along with the other server statistics.</p>
<h3>
<a id="user-content-server-dashboard" class="anchor" href="#server-dashboard" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Server dashboard</h3>
<p>In addition to the battery level, other information about the website server is visible with a statistics dashboard — these stats are simply pulled from the json. This includes contextual information of the server's location in Barcelona: the time, the current sky conditions, the upcoming forecast, and the duration since the server last shut down due to insufficient power. This is another effort to make the backend context of the website visible.</p>
<h2>
<a id="user-content-print-styles" class="anchor" href="#print-styles" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Print Styles</h2>
<p>The new version of the website features printer-friendly styling. Here, we wanted to challenge the assumption that consuming something digitally isn't necessarily more sustainable. Rather, if printing is necessary, we wanted to design a printed version that was as resourceful as its web counterpart, maximizing the page space.
Styling for printing is similar to styling for mobile devices — but instead of setting rules by break point, we use <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/Printing" rel="nofollow">print media queries</a>.</p>
<p><img src="https://camo.githubusercontent.com/3dfee1128bbc03e3166c21e4818496509441bce2/68747470733a2f2f6d617269656f7473756b612e6769746875622e696f2f626c6f672f696d672f7072696e747374796c652e706e67" alt="print preview" data-canonical-src="https://marieotsuka.github.io/blog/img/printstyle.png"></p>
<div class="highlight highlight-source-css"><pre><span class="pl-k">@media</span> <span class="pl-c1">print</span> {

}</pre></div>
<p>Among various typographic adjustments for print, a large modification was to condense the text into a 2-column layout to maximizes page width while maintaining a reasonable measure (width of paragraph.)</p>
<div class="highlight highlight-source-css"><pre>	<span class="pl-e">.entry-content</span> {
		<span class="pl-c1"><span class="pl-c1">columns</span></span>: <span class="pl-c1">2</span>; //<span class="pl-c1">number</span> <span class="pl-c1">of</span> <span class="pl-c1"><span class="pl-c1">columns</span></span> <span class="pl-c1">to</span> <span class="pl-c1">divide</span> <span class="pl-c1"><span class="pl-c1">up</span></span> <span class="pl-c1">the</span> <span class="pl-c1"><span class="pl-c1">content</span></span>
		<span class="pl-c1"><span class="pl-c1">column-gap</span></span>: <span class="pl-c1">20<span class="pl-k">pt</span></span>; //<span class="pl-c1">gutter</span>
	}
</pre></div>
<p>Some other considerations include avoiding images to break across pages. (This property has mixed browser support; some browsers inherently avoid this even without this css. )</p>
<pre><code>	p.img {
		page-break-inside: avoid;
	}

</code></pre>
<p>and displaying the URLs to linked texts — a technique borrowed from <a href="https://css-tricks.com/snippets/css/print-url-after-links/" rel="nofollow">CSS tricks</a>.</p>
<pre><code>	a:after{
		content:" (" attr(href) ") ";
		font-size: 0.8rem;
		font-weight:normal;
	}

</code></pre>
<h3>
<a id="user-content-sources" class="anchor" href="#sources" aria-hidden="true"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Sources</h3>
<ul>
<li>Frick, Tim. Designing for Sustainability: A Guide to Building Greener Digital Products and Services. O’Reilly Media, August 2016. <a href="http://shop.oreilly.com/product/0636920043904.do" rel="nofollow">http://shop.oreilly.com/product/0636920043904.do</a>
</li>
<li>Christie, James. "Sustainable Web Design." <a href="https://alistapart.com/article/sustainable-web-design" rel="nofollow">https://alistapart.com/article/sustainable-web-design</a>
</li>
</ul>

