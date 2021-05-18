# Formatting

## General

### Adaptable Content

One of the most important aspects of accessible design is creating adaptable content. This means that the content can be viewed on different screens and with different zoom levels without decreasing the quality of the user experience.

1.  **Ensure content can be zoomed in up to at least 200% without overflowing containers or requiring horizontal scrolling.** This goes hand-in-hand with general responsive design for mobile users. If you have ever tried to view a PDF on a mobile screen or with a high enough zoom level that you had to scroll horizontally, then you are probably aware of how frustrating it is for any user when content is not adaptable.
2.  **Do not require a particular orientation (horizontal vs. vertical) for viewing your website.**
3.  Create responsive content. **Make sure that your content adjusts and resizes appropriately for very small screens and very large screens.** Many browsers and other applications will allow you to preview your content as it would look for different sizes of screen. You may also be able to mimic this effect by zooming in or out, or by changing the size of your browser or application window.

### Style Sheets

CSS stands for Cascading Style Sheets. While CSS commands can be embedded directly inside HTML files, this is not recommended. Keeping your CSS in a separate .css file makes your code cleaner and makes it easier for users (and yourself) to override existing styles.

Be very wary of putting only some of your CSS in a separate file. Test your site with the style sheet turned off to ensure that it is still accessible. You may find that an embedded style is only accessible when combined when the CSS in your style sheet. This can become an issue if users need to turn off style sheets for any reason.

## Interactive Formatting

Interactive elements require special attention to make sure they are clear to all users.

1.  **Give all interactive elements clear style changes when they are hovered over or receive focus.** Hover is most commonly implemented, and makes it clear that clicking will activate the element. Focus is less often implemented, however. It is essential that users know where they are on a page when navigating with something other than a mouse.
2.  **Make clicking and hovering forgiving of imprecision** with [amply sized touch targets](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html), space between interactive elements, and forgiving mouse paths (e.g.: wide vertical dropdown paths remain open when a hovering mouse deviates a dozen pixels from a straight path; narrow horizontal flyouts would close).
3.  **Make it clear when buttons or other interactive components are disabled.** WCAG guidelines currently make an exception to the color contrast rules for disabled components, but this exception should really only apply to components that are not supposed to visually identifiable to any users. If a grayed about button would be visible to some users, make sure it has enough contrast to be visible to all users.
4.  **Visual indications that elements are interactive (links, buttons) should be clear and consistent, and should be reserved for interactive elements.** Users should not have to figure out what they can click on through trial and error. Color change may be one of these visual indications, but remember not to convey meaning through color alone.

### Links

For links, the standard formatting is blue and underlined. Because underlining is so commonly associated with links, it is inadvisable to change this. If blue does not fit with your color scheme, however, there is no reason you cannot change the color. It can also be useful to make it clear when a link has been visited, but this is not a requirement and the usefulness may depend on context.

The standard formatting for links on hover is to change the link color and turn the cursor into a pointer (the little hand icon). On focus, the only indication may be the browser's default outline. This is less than ideal. If you have the freedom to do so, it is well worth setting different formatting for focus and hover. 

[The WebAIM website](https://webaim.org/) is a stellar example of good focus and hover formatting for links. On both focus and hover, the link background and the link text change color, and a border is added at the top and bottom. On focus, the default browser outline is also added. Not only is this very accessible, it also looks cool and makes the links stand out to all users.

## Color

Color can be a great tool, but it must be used with care when creating accessible content. Beyond color contrast, here are a few other issues to consider when choosing colors:

1.  **Avoid communicating concepts with color alone.** Readers who are blind, low vision, or colorblind may miss out on important information if it is only shown via color. Secondary indications, such as icons, underlines or contrast changes may be needed to differentiate elements visually. You will also need to consider what screen reader users will hear to make sure they will receive the necessary concepts.
2.  **Consider colorblindness when determining color schemes**, especially when using any sort of color coding. Use colorblindness simulators to see what your color palette will look like to people with various kinds of colorblindness.
3.  **Avoid large blocks of brightly colored text.** These may be too distracting, or even cause a vibration afterimage effect.
4.  **Keep backgrounds subtle.** Bright or strongly textured/patterned backgrounds can make web pages hard to read.

### Contrast

Accessible content needs to meet a minimum acceptable level of color contrast. Fortunately, you don't have to figure out the ratios yourself, as there are many tools on the web you can use (although you can check the WCAG specifications to find the ratios, if you like). Several are included in the resources section further down. Bookmark your favorite so you can refer to it whenever you need.

1.  **Ensure background and foreground colors have sufficient contrast.**
2.  **Ensure background images have sufficient contrast with text.** This is often done by darkening the image and using light text or lightening the image and using dark text.
3.  **Avoid using contrast that is too extreme.** For example, pure black (#000) against pure white (#FFF) can actually be worse for some users, especially those with dyslexia or light sensitivity.

### Resources

-   [Vibrating Color Combinations](https://accessibility.psu.edu/color/brightcolors/) 

Examples of bright color combinations to avoid

-   [Textured Backgrounds](https://accessibility.psu.edu/color/colortexture/) 

Examples of good and bad background colors/images.

-   [Vischeck](http://www.vischeck.com/vischeck/vischeckImage.php) A tool for uploading images to see what they look like to someone with colorblindness
-   [Paletton](https://paletton.com/) Color palette picker that provides vision simulation for different types of colorblindness
-   [Coloring for Colorblindness](https://davidmathlogic.com/colorblind/) Color palette testing tool for protanopia, deuteranopia, and tritanopia
-   [Contrast Checker](https://webaim.org/resources/contrastchecker/) A simple color contrast checker provided by WebAIM
-   [Material Design Color Tool](https://material.io/resources/color/#!/?view.left=0&view.right=0) Color palette picker that checks contrast levels
-   [ColorCube](https://oomphinc.github.io/colorcube/) A color palette contrast checker
-   [Contrast Grid](https://contrast-grid.eightshapes.com/) A color palette contrast checker

## Text Formatting

When it comes to formatting text, two of the biggest topics that come up are font and text size. Many people recommend using relative font sizes instead of absolute to make it easier for users to modify the size. This is not a huge deal, as most browsers provide zoom capabilities, and users who require zooming probably have tools for this as well, but it might still be helpful for some people.

For content creators, there is no need to worry about this, especially since the text editor probably does not give you a choice. For developers, however, it is preferable to use relative font sizes, as well as to avoid setting font size for the `:root`, `<html>`, or `<body>` elements. This is because a browser's default font sizes will be accessible, and potentially customizable, as well.

Factors like letter spacing and line height can be changed with CSS. Whether or not this is necessary or helpful depends on the actual font used.

1.  **Avoid underlining text**, as underlines are typically reserved for indicating links.
2.  **Be wary of using strikethrough**. This formatting will not be passed to screen readers, and the line can make the text harder to read. Making the text slightly larger may help with the latter issue.
3.  **Use left alignment.** Left-aligned text maintains consistent character and word spacing. Inconsistently spaced words in justified text can make it difficult to read, and the inconsistent left alignment of centered or right-aligned text is often mistaken for meaningful tab indentations. (If you are writing in text that is supposed to be read from right to left, right alignment will likely be the better choice.)

### Font

A lot has been said about sans serif vs. serif font. Either type can potentially be accessible or inaccessible based on other characteristics of the particular font, so focus on font characteristics like height, weight, character spacing, character width, and how well the font distinguishes between ambiguous characters (e.g. 1 (one) vs. I (capital i) vs. l (lowercase L)) along with overall readability, instead.

1.  Highly recommended fonts include Verdana, Lucida Sans or Lucida Grande, and Georgia. Check out Penn State University's [font sample list](https://accessibility.psu.edu/fontfacehtml/#sample) for more options and comparisons.

### Bold and Italics

When it comes to the web, there are several ways that bold and italic formatting can be applied. For bold, there is the `<strong>` tag, the `<b>` tag, or the CSS rule `font-weight: bold`. For italics, there is the `<em>` tag, the `<i>` tag, or the CSS rule `font-style: italic`. Theoretically, the `<strong>` and `<em>` tags carry semantic meaning, while the other options are purely formatting. In practice, screen readers almost always ignore these tags. (This is similar to other semantic elements that apply formatting, such as `<cite>`, `<code>`, or `<del>`, that screen readers also tend to ignore.)

1.  It is nice if you can differentiate between meaningful and non-meaningful bold and italic formatting, but do not worry if that is not an option. (Most editors will only give you one option for each.)
2.  Italics can be hard to read on digital platforms. Consider using **bold** or **_bold and italics_** instead.

## Visual Layout vs. Structure

Formatting pages can make them very pretty, but moving elements around carries with it the risk of breaking the structural order. **The underlying structure of the page should be arranged in the order the elements should be experienced. The visual layout should then conform to the structural layout.**

One reason for this is to ensure sighted users and screen reader users have consistent experiences. Screen reader may be a deceptive name, because screen readers do not truly read what is on the screen. Instead, they access the underlying structure. Thus, any repositioning of elements with CSS will not apply to a screen reader user's experience.

What if the visual layout and underlying structure don't match up, but both orders make sense are reasonable ways to organize the page's contents? It is important to remember that many people with low-vision use screen readers, but do not rely on them fully. This means that they are experiencing both the visual page and the underlying structure at the same time. If the two are not consistent, this can quickly become extremely confusing and frustrating.

Two CSS rules to be especially careful with are `float: right` and `position: absolute`. There is no reason you cannot use these, but they do make it easy to rearrange elements in confusing ways.

### Hiding Content

There are many situations where you would want to hide content, and there are several ways to accomplish this. Before picking one, make sure to consider who you want to hide the content from - sighted users only, screen reader users only, or both (while keeping in mind that some people with low vision also use screen readers). Oftentimes, content hidden from one group will coincide with content hidden from another. For example, a symbol provided for sighted users might include alternative text for screen reader users.

Hiding content from everyone is often required when using interactive elements that reveal or hide additional information. For example, a tab list should only show one tab panel at a time, even though all of the tab panel content would be included in the page HTML. This is easy to accomplish in CSS using `display: none`, although this does prevent using fancy transitions when switching content. Another option would be to hide content visually and include `aria-hidden="true"` to also hide it from screen reader users. If you do this, do not forget to change the aria-hidden status when revealing the content!

Hiding content visually has a couple of common use-cases. Some content should be hidden until it receives focus. A common example is a page's "skip to main content" link. Hiding these can be accomplished through a variety of means, including positioning the object off-screen or making it transparent with `opacity: 0`. Penn State has [sample code for a basic skip link.](https://accessibility.psu.edu/skipnav/skiplinks/)

Other content may need to be hidden visually and never revealed. For example, Font Awesome icons are popular in user interfaces, but do not give any useful information to screen reader users. A good way to provide the needed information is to create a "sr-only" class that can be applied to a `<span>` with the text.

Finally, you may want to hide some content from screen readers. To use the above example, it is generally advisable to hide the Font Awesome icons, since they do not give any useful information to screen readers. Thus, you display the icon visually, but not to screen readers, and the alternative text to screen readers, but not visually. You can hide content from screen readers by including the property `aria-hidden="true"` in the element to be hidden.

## References

-   [Design Accessibly](https://accessibility.princeton.edu/how/design) Designer's guide focusing on legibility, color, flexibility, and intuitive interactions.
-   [Bold and Italic Formatting in HTML](https://accessibility.psu.edu/boldfacehtml/) 
-   [Contrast or Luminosity/Brightness](https://accessibility.psu.edu/legibility/contrast/) A variety of color contrast issues
-   [CSS (Styles)](https://accessibility.psu.edu/css/) Benefits of style sheets for accessibility and issues to avoid
-   [Font Face on the Web](https://accessibility.psu.edu/fontfacehtml/) Includes a useful list of recommended fonts.
-   [Accessible Font Sizing, Explained](https://css-tricks.com/accessible-font-sizing-explained/) 
-   [Is it ok to ‘grey out’ disabled buttons?](https://uxdesign.cc/is-it-ok-to-grey-out-disabled-buttons-8afa74a0fae)
