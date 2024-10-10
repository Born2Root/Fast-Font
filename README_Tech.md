# How it works (the technical side):

Here you can take a look behind the scenes and understand how the font works.
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

Regarding the bold rules, I used a simple table to calculate how many characters should be formatted bold.
The formula calculates, for example, how many characters are 40% of the word length, rounded to a full number afterwards.
(Please be aware that I used the 40% rule starting with 5 character long words. For all shorter words I just defined the number of characters without any calculation)

![tech_bold_rules](https://github.com/user-attachments/assets/12e20a98-a4f3-4ac9-9236-acb463d883ba)

As a result you can see, that some word-lenghts result in the same number of characters formatted bold.
Thats why certain word-lengths are combined to one ruleset in the OpenType program code.
The ignore line specifies what to not replace.
The sub line specifies which characters to replace as bold.
To change the formattign rules just change the position of the @az' command within each feature rule.
In this way you can format more or fewer characters per word-lenght bold.
And of course it is possible to define much more rules. For instance one separate rule for each word lenght, without a combination like I did.

![tech_example](https://github.com/user-attachments/assets/8905b32c-cf14-431d-81bc-1750a4d19001)


# Variation:
You can change the behaviour of the font by changing the code and changing the glyphs.
Possible is for example:

-   Choose your fixation. How much of a word should be bold.
-   Change the opacity of the bold letters.
-   Apply to every font you want.
-   Or use italic instead of bold.


You can find a whole Tutorial on how to change the typeface and adapt the rules to another font on this page:
[Tutorial](https://github.com/Born2Root/Fast-Font/blob/main/README_Tutorial.md)



  
