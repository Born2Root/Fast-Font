# Fast Font

> **A** **fo**nt **t**o **he**lp **y**ou **re**ad **fas**ter.

This font provides faster reading through facilitating the reading process by guiding the eyes through text with artificial fixation points. As a result, the reader is only focusing on the highlighted initial letters and lets the brain center complete the word. This allows you to read in supersonic speed.

The project is completely open-source, so please feel free to use and distribute it however you want.

![Demo GIF](https://github.com/Born2Root/Fast-Font/blob/main/docs/Fast-Font.gif)

## Demo:

[DEMO wich supports live text input](https://Born2Root.github.io/Fast-Font)

[DEMO wich converts a PDF with the fast-reading-fonts](https://huggingface.co/spaces/Sanshruth/Bionic_Reading_Hub)

For local testing, open [test.html](https://github.com/Born2Root/Fast-Font/blob/main/docs/test.html) in your browser.


Don't miss to check out our [other font projects!](https://github.com/Born2Root/Feature-Fonts) 👍

---

## ✨ Variations:

At the moment we have five different variations of the Fast-Font available.
The first three are best suited for reading and offer support for the most languages.
The Monospaced version is the best fit if you want to use it in an coding environment.

**1. Fast Font with Serifs:**
   ![image](https://github.com/user-attachments/assets/4dae6fbf-34da-4492-be71-b04ac12a2a9f)

**2. Fast Font Sans (without Serifs):**
   ![image](https://github.com/user-attachments/assets/dea53742-c051-4165-bac9-dabf47b2e5ac)

**3. Fast Font Sans (without Serifs) and Dots as spaces:**

This Font is inspired by the Space Reading® technique Kam Knight discusses in his book [*"Speed Reading: Learn to Read a 200+ Page Book in 1 Hour"*](https://amzn.to/3U6RYYb).
The basic idea is to not concentrate on the single words but looking at the white spaces between every 3-4 words. Paying attention on the spaces prevents the eyes from narrowing the focus, thus we are able to pick up more peripheral information. At the beginning it can be quite challenging focusing on the white spaces. 
This Font helps you by inserting a litte dot, that is much easier to focus.
   ![image](https://github.com/user-attachments/assets/c2614801-77b1-433f-b781-6b8655dbb862)

**4. Fast Font Monospaced:**

Monospaced version intended for use in coding environment. It also supports coding ligatures. Please refer to the [FiraCode Ligature Documentation](https://github.com/tonsky/FiraCode/blob/master/extras/ligatures.png) as a reference.
![image](https://github.com/user-attachments/assets/6292b0b1-d7b4-4a37-8d8b-611dee0c9820)

**5. Fast Font Dyslexic:**

This Font is based on the [OpenDyslexic](https://opendyslexic.org/) typeface designed against some common symptoms of dyslexia.


---

## ⁉️ How to use the Font:

### Use in Software
In MS-Word, select the text and enable "Use Contextual Alternates" in the OpenType Features.

![M$ Word](https://github.com/Born2Root/Fast-Font/blob/main/docs/word.jpg)

You can also use it for programming, i.e. in VSCodium.
Just select your font and set `"editor.fontLigatures": true,`.

Or use it as the default font in your browser:

![Example.com with new sans-serif font](https://github.com/Born2Root/Fast-Font/blob/main/docs/browser.jpg)

### Use on Kobo eReader

If you have a Kobo Reader with KoReader-Extension you can also use it there.
Please refer to the [Github Issue](https://github.com/Born2Root/Fast-Font/issues/1) and the  [Corresponding Reddit Post](https://www.reddit.com/r/kobo/comments/186y8m7/speedreading_bionic_font_fast_font_working_on/?rdt=54785)

![IMG_20231129_112326774 (1)](https://github.com/Born2Root/Fast-Font/assets/149900376/9d81c868-5fae-4a88-8820-9d7c64959391)

### Use on Kindle

If you have a Kindle there are 4 easy steps to transfer the Fast-Fonts.

**Step 1:** Connect your Kindle to your computer<br>
- Use a USB cable to connect your Kindle to your computer. Your Kindle should appear as a drive on your computer.

**Step 2:** Transfer the Font Files<br>
- Open the "Kindle" drive on your computer.<br>
- Download the fonts from this repository.<br>
- Locate the "fonts" folder. If it doesn’t exist, create a new folder and name it "fonts".<br>
- Copy the downloaded font files into this folder.

**Step 3:** Safely Eject Your Kindle<br>
- After transferring the font files, safely eject your Kindle from your computer to ensure the files are properly saved.

**Step 4:** Select the Font on Your Kindle<br>
- Open a book on your Kindle.<br>
- Tap the top of the screen to access the toolbar.<br>
- Tap the "Aa" icon to open the display settings.<br>
- Go to the "Font" tab and select the Bionic Reading font you installed.

It seems Kindle handles fonts different depending on the source of the books (bought from the store vs. loaded locally from Calibre).
If you are having trouble to get the Font working on Kindle, please refer to the [Github Issue](https://github.com/Born2Root/Fast-Font/issues/8) 

ATTENTION: Please be aware that only the new Kindles are that easy to handle. If you have an older Kindle (below 5th generation) please refer to the [Github Issue](https://github.com/Born2Root/Fast-Font/issues/8) 

## Advantages:

-   free and totally open-source
-   from personal use to business. Web, Desktop, App/ Game, eBook, use it wherever you want
-   offline usable. No internet connection necessary
-   fast, no (additional) client-side code
-   compatible with existing programs
-   privacy respecting

---

## ⚙️ How it works (the technical side):
Are you interested in the technical aspects of the Fast-Font?
You can find a detailed description about the background technology here: [Tech-Guide](https://github.com/ThereOHM/Fast-Font/blob/main/README_Tech.md)

## How to apply the Speed-Reading feature to other Fonts:

Apply the shown feature to any font you like. For example, using the [`addfeatures.py` script](https://github.com/simoncozens/test-fonts/blob/master/addfeatures.py).
If you prefer an WYSIWYG-Editor I can really recommend "[FontLab](https://www.fontlab.com/)", "[FontCreator](https://www.high-logic.com/font-editor/fontcreator)" or "[Font-Forge](https://fontforge.org/)". 

To give you an introduction on how to do this, you can find an elaborate Tutorial for "FontLab 7" here: [Tutorial](https://github.com/Born2Root/Fast-Font/blob/main/README_Tutorial.md)

To use the font in other languages world wide it is necessary to enrich it with the appropriate characters and their substitution.
With about 120 special characters nearly all European languages are covered.
See [opentype_feature.fea](opentype_feature.fea) for an elaborate example.

---

## ❤️ Support:

The fonts stored in this repository are provided free of charge.
If you like the project, we would appreciate your support.

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/born2root)

---

## 📖 Additional Information

### Book Recommendations:

If you want to dive deeper into speed reading I can really recommend the following books.

**English:**
-   [The Speed Reading Book - Tony Buzan](https://amzn.to/3Edhxl9)
-   [Speed Reading: Learn to Read a 200+ Page Book in 1 Hour - Kam Knight](https://amzn.to/3U6RYYb)
-   [The Complete Idiot's Guide to Speed Reading](https://amzn.to/3ClA12m)

**German:**
-   [Speed Reading fürs Studium - Günther Koch](https://amzn.to/4hcuf2i)
-   [Bewährte Speed Reading Techniken](https://amzn.to/3WzGZHI)

### Alternative Solutions for Fast-Reading Font:

-   https://github.com/ansh/jiffyreader.com
-   https://github.com/ahrm/chrome-fastread
-   https://github.com/boldreader/chrome-extension / https://github.com/akay/firefox-fastread
-   https://boldreader.github.io/boldreader/

### Useful Links:

-   https://blog.readwise.io/bionic-reading-results/
-   https://forum.high-logic.com/viewtopic.php?t=6723
-   https://forum.high-logic.com/viewtopic.php?p=26623#p26623
-   https://sparanoid.com/lab/opentype-features/
-   https://simoncozens.github.io/test-fonts/#fallbackplus-regularotf
-   https://adobe-type-tools.github.io/afdko/OpenTypeFeatureFileSpecification.html#example-3-1
-   https://www.typenetwork.com/news/article/opentype-at-work-contextual-alternates
