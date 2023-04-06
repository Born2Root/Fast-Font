# Fast Font

> **A** **fo**nt **t**o **he**lp **y**ou **re**ad **fas**ter.

This font provides faster reading through facilitating the reading process by guiding the eyes through text with artificial fixation points. As a result, the reader is only focusing on the highlighted initial letters and lets the brain center complete the word. This allows you to read in supersonic speed.

![Demo GIF](Fast-Font.gif)

## Demo

[DEMO](https://Born2Root.github.io/Fast-Font)

## How it works

The basic idea is to substitut the first few letters with their bold variant.

You can define how much should be fixated. A rule of thumb would be something like:

> If there are <= 3 letters, one letter is bold.
>
> If there are == 4 letters, two letters are bold.
>
> If there are > 4 letters, 40% of all letters are bold.

The rules can be applied using OpenType Font features.
Here is a basic example usage of "Contextual Alternates" (calt) substitution:

Having the word "font". OpenType goes through the rules from top to bottom for each letter.

1. The code analyzes the position of the current letter `@az'` inside a word.
1. Starting with "f" only the last `sub` matches as it only ever matches the first letter.
1. On letter "o" the first `sub` matches as there is one previous and two following letters.
1. For the other letters, there are no matching rules.

```fea
feature calt {
    @az = [a-z A-Z];
    @AZ = [a.bold-z.bold A.bold-Z.bold];

    @all = [@az @AZ];

    # 4, 5, 6
    ignore sub @all @all @az' @all @all;
    sub @all @az' @all @all by @AZ;

    # 1, 2, 3
    ignore sub @all @az';
    sub @az' by @AZ;
} calt;
```

Apply this feature to any font you like. For example, using the [`addfeatures.py` script](https://github.com/simoncozens/test-fonts/blob/master/addfeatures.py).

To use the font in other languages world wide it is necessary to enrich it with the appropriate characters and their substitution.
With about 120 special characters nearly all European languages are covered.
See [opentype_feature.fea](opentype_feature.fea) for an elaborate example.

### Variation:

-   Choose your fixation. How much of a word should be bold.
-   Change the opacity of the bold letters.
-   Apply to every font you want.
-   Or use italic instead of bold.

## How to use:

In Word, enable "Use Contextual Alternates" in the OpenType Features.

![M$ Word](word.jpg)

You can also use it for programming, i.e. in VSCodium.
Just select your font and set `"editor.fontLigatures": true,`.

Or use it as the default font in your browser:

![Example.com with new sans-serif font](browser.jpg)

## Adavantages:

-   free
-   offline
-   fast
-   no (additional) client-side code
-   compatible with existing programs
-   privacy respecting


## Support:

The fonts stored in this repository are provided free of charge.
If you like the project, we would appreciate your support.

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/born2root)


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
