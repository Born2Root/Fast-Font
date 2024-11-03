# Intro
I was recently active with FontLab again, so I decided to make a little tutorial to make it easier for other users to get active.
Aim of the small tutorial is to show, how you can apply the fast-reading features to any other font.
I am using the software "FontLab version 7", but you can also use any other capable software.

# Selecting & preparing the Font

First of all, you need a font that you want to enritch with the speed-reading feature.
Since the speed-reading feature uses bold-characters you need two versions of the font:
- a regular or light version
- the bold version

Depending on the font you selected these two versions are already combined in one single font-file (.ttf or .otf).
Or also very common separated in two separate font-files, one containing the regular and one containing the bold version.
Because the Speed-Reading font is at the end only one single font-file, first of all we have to combine the two versions.

To achieve this, first open the bold version in Font-Lab.
Because we want to address the bold version with our code later on, we need to give every glyph a specific name.
Select all glyps in the character overview by clicking one and afterwards pressing "Strg + A".
Then go to "Font -> Rename Glyphs -> Suffix"

As a suffix choose ".bold" and press ok.

![bold rename](https://github.com/user-attachments/assets/74732c06-06d9-4ffc-be85-58a23d041554)

Afterwards every glyph of the font should have a name with the extension .bold

# Combining the Fonts
Now we have to combine the bold version and the regular/ light version in one file.
To do this, also open the regular/ light version in FontLab.
Select all glyphs from the bold version that we just renamed (easiest by pressing Ctrl + A) and copy them (Ctrl + C) or right click, Copy.

Now switch the Tab to the regular version and paste the copied glyphs to the font (Ctrl + V, or Paste).
A pop-up window will appear asking you how to insert the glyphs.
Select "Append glyphs, keep existing glyphs unchanged"

![append](https://github.com/user-attachments/assets/feb74a2e-fe71-4ebd-ac21-a8c4a6b01bc9)

Ok, now you should have the regular glyphs and the bold glyphs together in one file.

# Applying the Features to the Font

Now we prepared everything to get started with the real magic.
Open the "Feature" Panel if it is not already visible.
![Open Feature Panel](https://github.com/user-attachments/assets/b2caa1f3-2bde-4349-ac45-7553abb68f4e)

Now you can start adding OpenType features (the intelligence/ program code of the font).
The one that is use for the bionic speed reading functionality is "calt" contextual alternatives.
If it is not already included in the font you can add it via the + symbol.

Afterwards just add the whole program code that you can find in the repo.
[opentype_feature.fea](https://github.com/Born2Root/Fast-Font/blob/main/opentype_feature.fea)

![Feature Description](https://github.com/user-attachments/assets/aa739c59-d70d-487f-ab31-12502da84975)

In the mentioned .fea file of the repo are a lot of special glyphs used, to cover nearly all special characters of all languages worldwide.
It is very likely, that the font that you selected will not contain all these special characters.
Running the program code, by clicking the little "Play" icon, will therefore probably result in a couple error messages.

![run](https://github.com/user-attachments/assets/75cdcb27-b33b-4b26-9e5b-817a4a48bfdd)

Errors can look like this, where FontLab tells you which glyphs are missing.
![error](https://github.com/user-attachments/assets/e68ab725-1ea7-4289-a83a-d28f2d232fe1)

That means, that there are more letters/ glyphs covered in the program code of the "Fast-Font", than that there are existent in your font.
As an explanation, the first line with "Missing glyph: uni0334 -> uni1D6C" tells you that the Unicode-Character uni1D6C is missing in the Bookerly.ttf. Looking the character up on the web tells you that it is a character from the greek alphabet, that is not covered.

There are two ways to fix this:
- Design the characters that are missing yourself. You can do that with FontLab, but you need at least some designer abilities.
- Much easier, and what I would recommend: Just remove all the code-lines that are related to the characters that the error is mentioning.

The completely to the latin base characters reduced code looks like this.

```
feature calt {

@az = [a-z A-Z];
@AZ = [a.bold-z.bold A.bold-Z.bold];

@all = [@az @AZ];
	

#17
		ignore sub @all @all @all @all @all @all @all @az' @all @all @all @all @all @all @all @all @all @all;
		sub @all @all @all @all @all @all @az' @all @all @all @all @all @all @all @all @all @all by @AZ;

#14,15,16
		ignore sub @all @all @all @all @all @all @az' @all @all @all @all @all @all @all @all; 
		sub @all @all @all @all @all @az' @all @all @all @all @all @all @all @all by @AZ;

#12,13
		ignore sub @all @all @all @all @all @az' @all @all @all @all @all @all; 
		sub @all @all @all @all @az' @all @all @all @all @all @all @all by @AZ;

#9,10,11
		#ignore sub @all @all @all @all @az' @all @all @all @all @all @all; 
		ignore sub @all @all @all @all @az' @all @all @all @all @all; 
		sub @all @all @all @az' @all @all @all @all @all by @AZ;

#7,8
		ignore sub @all @all @all @az' @all @all @all @all; 
		sub @all @all @az' @all @all @all @all by @AZ;

#4,5,6
		#ignore sub @all @all @az' @all @all @all; 
		ignore sub @all @all @az' @all @all;
		sub @all @az' @all @all by @AZ;

#1,2,3 
		ignore sub @all @az';
		sub @az' by @AZ;

} calt;
```

Use that as a starting point to get the whole font running. Add the special characters that you need afterwards.
For example it would be necessary to add some lines for the "ö ü ä ß"

```
@de = [adieresis odieresis udieresis Adieresis Odieresis Udieresis germandbls];
@DE = [adieresis.bold odieresis.bold udieresis.bold Adieresis.bold Odieresis.bold Udieresis.bold germandbls.bold];
	
@sp = [@de];
@SP = [@DE];

@az = [a-z A-Z @sp];
@AZ = [a.bold-z.bold A.bold-Z.bold @SP];
```
For other special characters just add them from the "EU languages" section or the cyrillic section "RU = russian, cyrillic" of the original program code.
Please again, be aware that you need a font covering the special characters that you need, or design them yourself.
[opentype_feature.fea](https://github.com/Born2Root/Fast-Font/blob/main/opentype_feature.fea)

If the test of the font works, and if you don't get any more errors it's time to export our font.

## Preview the Font

If not already visible activate the "Preview Panel" in the Window-Settings.
Afterwards you can start typing a text in the preview window and it automatically applies your font and open type features.

![Fast Font Tutorial - activate Preview](https://github.com/user-attachments/assets/323db692-293a-4d08-90f3-0c2ee6c06d71)


## Export the Font
If you want the speed reading variation of the font alongside the original font, you should rename it.
To do this click on the little information "I" and change the name in the following window.
I would recommend to just add a suffix to the font, like Fast or Speed.

![Font-Umbenennen](https://github.com/user-attachments/assets/42258ce1-d735-4cc7-bd61-c1dde7f24f87)

Now you can go to "File --> Export Font", choose a file-format your operating-system supports.
Most likely .ttf or .otf.
Export the Font to a desired folder and use it in any other application...

Have Fun!



