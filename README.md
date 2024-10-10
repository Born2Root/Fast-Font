# Fast Font

> **A** **fo**nt **t**o **he**lp **y**ou **re**ad **fas**ter.

This font provides faster reading through facilitating the reading process by guiding the eyes through text with artificial fixation points. As a result, the reader is only focusing on the highlighted initial letters and lets the brain center complete the word. This allows you to read in supersonic speed.

![Demo GIF](Fast-Font.gif)

## Demo:

[DEMO](https://Born2Root.github.io/Fast-Font)

---

## Variations:

At the moment we have three different variations of the Fast-Font available.

**1. Fast Font with Serifs:**
   ![image](https://github.com/user-attachments/assets/d1275aec-4781-42f4-9fbf-9a968d01c1ea)

**2. Fast Font Sans (without Serifs):**
   ![image](https://github.com/user-attachments/assets/dea53742-c051-4165-bac9-dabf47b2e5ac)

**3. Fast Font Sans (without Serifs) and Dots as spaces:**
   ![image](https://github.com/user-attachments/assets/5e77c4ff-2b55-4c2d-acf5-1f9e0b3fc08e)


## How to use the Font:

In Word, enable "Use Contextual Alternates" in the OpenType Features.

![M$ Word](word.jpg)

You can also use it for programming, i.e. in VSCodium.
Just select your font and set `"editor.fontLigatures": true,`.

Or use it as the default font in your browser:

![Example.com with new sans-serif font](browser.jpg)

If you have a Kobo Reader with KoReader-Extension you can also use it there.
Please refer to the [Github Issue](https://github.com/Born2Root/Fast-Font/issues/1) and the  [Corresponding Reddit Post](https://www.reddit.com/r/kobo/comments/186y8m7/speedreading_bionic_font_fast_font_working_on/?rdt=54785)

![IMG_20231129_112326774 (1)](https://github.com/Born2Root/Fast-Font/assets/149900376/9d81c868-5fae-4a88-8820-9d7c64959391)

## Advantages:

-   free
-   offline
-   fast
-   no (additional) client-side code
-   compatible with existing programs
-   privacy respecting

## How it works (the technical side):
Are you interested in the technical aspects of the Fast-Font?
You can find a detailed description about the background technology here: [Tech-Guide](https://github.com/ThereOHM/Fast-Font/blob/main/README_Tech.md)

## How to apply the Speed-Reading feature to other Fonts:

Apply the shown feature to any font you like. For example, using the [`addfeatures.py` script](https://github.com/simoncozens/test-fonts/blob/master/addfeatures.py).
If you prefer an WYSIWYG-Editor I can really recommend "[FontLab](https://www.fontlab.com/)", "[FontCreator](https://www.high-logic.com/font-editor/fontcreator)" or "[Font-Forge](https://fontforge.org/)". 

To give you an introduction on how to do this, you can find an elaborate Tutorial for "FontLab 7" here: [Tutorial](https://github.com/Born2Root/Fast-Font/blob/main/README_Tutorial.md)

To use the font in other languages world wide it is necessary to enrich it with the appropriate characters and their substitution.
With about 120 special characters nearly all European languages are covered.
See [opentype_feature.fea](opentype_feature.fea) for an elaborate example.

## Support:

The fonts stored in this repository are provided free of charge.
If you like the project, we would appreciate your support.

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/born2root)

---

## Alternatives:

-   https://github.com/ansh/jiffyreader.com
-   https://github.com/ahrm/chrome-fastread
-   https://github.com/boldreader/chrome-extension / https://github.com/akay/firefox-fastread
-   https://boldreader.github.io/boldreader/

## Useful Links:

-   https://blog.readwise.io/bionic-reading-results/
-   https://forum.high-logic.com/viewtopic.php?t=6723
-   https://forum.high-logic.com/viewtopic.php?p=26623#p26623
-   https://sparanoid.com/lab/opentype-features/
-   https://simoncozens.github.io/test-fonts/#fallbackplus-regularotf
-   https://adobe-type-tools.github.io/afdko/OpenTypeFeatureFileSpecification.html#example-3-1
-   https://www.typenetwork.com/news/article/opentype-at-work-contextual-alternates
