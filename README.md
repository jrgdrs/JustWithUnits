![Bildschirmfoto 2025-05-31 um 17.24.00.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/8F901933-F8EE-4619-9E55-ABF37EB883EB_2/aK6MdB9y1Hv3UyTwvgD0FGkp4VCsYhdCBnOzQNOJq8kz/Bildschirmfoto%202025-05-31%20um%2017.24.00.png)



#### Narrow column widths in newspaper and magazine typography often form rivers of white space and create an uneven appearance that limits legibility. This work is an attempt to compensate for these limitations and revive historically lost solutions with the latest font technology.



![Bildschirmfoto 2025-05-31 um 17.27.59.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/78A76F8D-F8EC-46D2-9FD1-F832D503461A_2/N7aJNWBsV2d47E1tb1rpylW3XV1DKxjPb3BizkZFzEAz/Bildschirmfoto%202025-05-31%20um%2017.27.59.png)

*Fig.1: Gutenberg (above) and Griffo (below) employed variants of different widths to create a smooth and varied flow of movement*



Even in the early days of letterpress printing, Johannes Gutenberg (ca. 1400-1468) and Francesco Griffo (1450-1518) used different widths of the same letters to achieve a balanced line pattern. This traditional method has been lost in the course of technical development. In this work, the functions are revived with the help of modern technologies such as Opentype fonts and the quality is evaluated using a series of tests. An important basis for this is the consideration of patterning, in which the regularity required for a smooth block surface of paragraphs begins with the individual letters. The restriction to the underlying patterns in the rhythm of the typeface is intended to maintain the orderly structure and avoid distractions in the reader's perception. By taking into account the classic design patterns of Latin fonts, the flows that occur when using justified text in narrow columns can be balanced out, creating a smoother, more even structure and increasing the readability of the text.

# Process

As part of the EcTd lessons, we used the DTL LetterModeler® to develop a Roman font model (german term: Renaissance Antiqua), to which we added further characters based on the word “Imperial”, and then came to the point of combining letters with different character widths into classes with the same width. In this task, all characters are first brought to a valid width that corresponds to a cadence level derived from the pattern of the respective font. **The cadence is determined as the stem interval of the lowercase /n and calibrated as an integer value, called a unit or step, approximating a quarter of the stems width.** The next step is to combine the different widths into as few classes as possible and, if necessary, to adapt the shapes of the characters accordingly. When working on this task, I found that the character widths could not always be clearly defined due to my internalized ideas of proportions. This meant that several variants could be valid in the same character set without disturbing the frequency of the cadence. So I came up with the idea of preserving the variants and providing them in a variable font. I recalled prototypical procedures with multiple master fonts from thirty years ago as a possible use for the width variants and discovered a potential use for improving justification. After initial research, the topic intrigued me and I decided to set this task for my personal project.

# Preanalysis

For an anticipated experiment, I first added changing widths for the most common characters in the German language (e, n, i, r, s, t, a, d, h) to my version of the exercise with the open font CALT (character alternative) and created a sample set with this font, which I presented to my fellow students. They confirmed that the different widths were not immediately or easily recognizable.



[OHamburgC-calt.pdf](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/d1c263a3-9229-02c1-76b0-1952ab273c86)

*Attachment 1: Test typesetting to check the conspicuousness of deviating character widths*



# Kick off

For the briefing, I created a presentation titled “Unit based width variants of glyphs for balanced justification” that summarizes my preliminary analyses.



[Unit based width variants of glyphs for balanced.pdf](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/0b964cfa-8f36-c242-83dd-4716fdbbb606)

*Attachment 2: Briefing presentation*



One of the suggestions I took away from the presentation was to also consider optical edge compensation.

# Setting up a test environment

To ensure that the tests required for the evaluation can be created as easily and reproducibly as possible, I looked for existing methods that already have functions for generating justification texts.

I first came across the repository of Simon Cozens, whose name I already knew from the Google Fonts team.

[https://github.com/simoncozens/newbreak](https://github.com/simoncozens/newbreak)

The newbreak software package already provides many functions for line breaks and justification with variable fonts and source-oriented parameterization.



![CropperCapture[331].png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/1f01d7ad-c1ac-2a39-f525-b2d87487a39b)

*Fig.2: User interface of the solution prepared by Simon Cozens*



I also found what I was looking for at Bram Stein, whose name I already knew from his hyphenation algorithm.

[https://github.com/bramstein/hyphenation-justification-vf](https://github.com/bramstein/hyphenation-justification-vf)

The hyphenation-justification-vf software package offers a simpler interface with result-oriented parameterization and provides many other functions that support my tests, such as paragraph hyphenation, calculation of a score and interactive highlighting of extra-wide spaces between words.



![CropperCapture[332].png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/3ff1fcf0-f8e7-8f69-9eac-2ef1c6566ca1)

*Fig.3: User interface of the solution prepared by Bram Stein*



After the comparison, I decided to use Bram Stein's package as the basis for my test procedures and only had to add the required procedures for character scaling (none, traditional, variable, unitized), the optical margin compensation and my variable font with test text and adapt the user interface. In addition, I added the print-binding page output of PDF documents. 



![CropperCapture[333].png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/63058aac-af91-3e32-e19b-e317a7df6d6b)

*Fig.4: User interface of the solution used here*



The solution runs in any browser, even locally standalone, and is available at github.com

[https://github.com/jrgdrs/UniBaWiVa](https://github.com/jrgdrs/UniBaWiVa)

# Scaling procedure

To carry out the tests, I integrated four different character scaling methods to compare the whitespace reduction:



![CropperCapture[334].png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/9d81fb30-7030-0f1f-b087-a6b66ccf951a)

*Fig.5: Comparison of character scaling methods*



- “Original” corresponds to the display without scaling the glyphs (none).  The remaining spaces are filled with whitespace.
- “Traditional” corresponds to the disproportionate geometric scaling of the glyphs used in Indesign, i.e. stretching in the x-direction. I have configured a maximum of 10 percent for the scaling; any remaining space is filled with whitespace. However, this changes the stroke widths of the vertical stems, the diagonals and, in the case of italic fonts, also the angle. This fact was met with incomprehension when it was introduced in Indesign®, as users had hoped that Adobe would also take intelligent scaling into account after acquiring the rights to use the hz program from Hermann Zapf and Peter Karow, but this is still not the case today.
- “Variable” corresponds to the modification of the width axis for variable fonts (wdth).  I have configured a maximum of 15 percent for the scaling; any remaining space is filled with whitespace. A value of 100 is assumed for the normal style, a reduced value for the condensed version and a higher value for the extended version, corresponding to the proportional character width in relation to the normal style. For fonts that use other scales, the values must be calibrated and adjusted accordingly.
- “Unitized” is a scaling function specially adapted for this purpose, which takes into account the cadence levels referenced in the font as well as optimizing the filling of the lines based on the possibilities. The cadence levels were mapped in the font at the beginning of the project in the counter-width axis “XTRA”, where 300 is the width of the inner space (counter) of the lowercase letter /n used in the normal section on the basis of 1/1000 EM. In the course of further iterations of development and testing, the procedure was changed, as described in detail below.



![CropperCapture[335].png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/e0a94b35-1123-19ce-71c4-e41fdb251826)

*Fig.6: The provided axes of a variable font can be checked with tools such as Axis-Praxis, here the three axes used in the test font for with Weight, Counter Width and Width axis.*



# Unitized procedure

The mode of operation is based on the practiced procedure as it was classically practiced for centuries in the typesetting technique used for letterpress printing.



![CropperCapture[329].png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/2e6551ad-52bc-9cf7-7665-e180ec498cd2)

*Fig.7: Traditional manual typesetting: As soon as no more characters fit into the composition stick, the necessary space between the lines is filled with spaces of different widths.*



I also found a video that shows the method of exchanging characters with different widths, also with the font Wilhelm Klingspor Gothic, designed in 1920 by Rudolf Koch, cast in Offenbach am Main, which has a wide and a narrow form for upper and lower case letters. 

*By the way, it is a sign of complete incompetence and academic misdirection that this video from Gutenberg University Mainz had to be recorded at the Museum der Arbeit in Hamburg when there was no technical expertise on site. Also The last type founder in Germany, Rainer Gerstenberg, is currently in an equally dire situation, as he is no longer allowed to use his casting machines set up in the Hessian State Museum in Darmstadt because building regulations would prevent this. I am therefore all the more grateful that we have comprehensive access to the originals at the Plantin-Moretus Museum so that we can carry out applied research.*



[Johannes Gutenberg (2/8): The art of manual typesetting](https://www.youtube.com/watch?v=CP_Q4NquVTE)

*Video 1: Manual typesetting with width variants*



The following procedure is carried out: 

- First, the text is examined for possible hyphenation joints and divided into segments using soft hyphens.
- The resulting sentence width of the segments is then measured on a trial basis using the normal cut and divided by a line breaking algorithm, taking into account the minimum width of the space between the words and the width of the hyphen. In the tests carried out here, the Knuth-Plass algorithm is used, which, as a “paragraph setter”, selects the variant that produces the smallest overall spaces between words in the paragraph when comparing different separation results. The alternatively available Greedy algorithm only considers one line at a time during optimization and is also referred to as a “line setter”.
- In this calculation, the width of the separator and the punctuation characters defined as overshooting is reduced by the specified factor (optical margin). The following characters were defined for this: overshootChars = [“-”, “.”, “:”, “,”, “;”]. For reasons of efficiency, the adjustment was only taken into account at the right-hand edge of the sentence during implementation.

    *It is worth mentioning that the minus-hyphen (hex 2d) had to be replaced by the hyphen (Unicode hex 2010 - Hyphen) and the character had to be added to the font, as modern browser versions use the line separator and treat this character differently for accessibility reasons, e.g. the character should not be read out in audio output (topic: dehyphenation).*

- Finally, the above-mentioned functions for glyph scaling are used.
- With unitized scaling, the whitespaces that exceed the minimum are cumulated for each line. As long as excess white space remains, it is determined for each character according to the number of occurrences in the line and the configured sequence whether it is possible to expand this character for all occurrences in the line. Accordingly, all characters are expanded or not. The order in which this is checked was defined based on the increasing visual conspicuousness of a widening in the configuration. Thus 
    - first the open round shapes without cadence-forming punches (e, c, s, a),
    - the simple stems (i, f, r, t),
    - then the diagonals (x, w, v, z),
    - then the cadence-identical round forms (p, b, q, d, g) and
    - finally the cadence-forming vertical stems (m, h, u, n)
    - as well as the eye-catching round shape (o)

    exchanged. In the program referred to as needles = [ 'e', 'c', 's', 'a', 'i', 'f', 'r', 't', 'x', 'w', 'v', 'z', 'p', 'b', 'q', 'd', 'g', 'm', 'h', 'u', 'n', 'o' ].

    

![Bildschirmfoto 2025-05-31 um 17.29.38.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/8D040B5A-C6D1-4A78-9C84-9079B3C5915D_2/GQIzGBCuCzoxg41aAMaX16dAC4y7VHdy5LMcLXKaI6Iz/Bildschirmfoto%202025-05-31%20um%2017.29.38.png)

*Fig.8: Comparison of the set character widths with regard to the conspicuousness of the differences. To decide which characters should be used and in which order, the conspicuousness of the changes was ranked using the examples.* 



- The formatting is then changed for these characters so that the variant that is exactly one cadence wider is displayed. I spent a long time looking for a way to preserve the undercuts between characters with different formatting. Unfortunately, neither a classic format change nor the adjustment of an axis parameter or an OpenType function offers the possibility of preserving the pair kerning. I have therefore extended the format change to the letter preceding the character if this is an uppercase letter. Within the font used, the capital letter remains identical in width, but the kerning also defined for this axis position is used as desired in this case.  



![Bildschirmfoto 2025-05-31 um 17.30.44.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/372D61CE-D5C5-4368-99B6-6BF3B45FCAC6_2/J3FwEKbSWPSQnsiCQ8OuE3Vxp171INPxFgVF88HXQGcz/Bildschirmfoto%202025-05-31%20um%2017.30.44.png)

*Fig.9: By widening the characters, here /e, /c, /s, /a, /i, /f, /r, /t, the whitespace is reduced to a minimum*



- It should also be mentioned that the test implementation accumulates all remaining spaces in the lines that exceed the configured minimum. This value is referred to as penalty, determined for each paragraph and displayed in the browser console for statistical purposes.



![Bildschirmfoto 2025-05-31 um 17.31.28.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/5EED0680-E262-40EF-866D-43CC680E67C4_2/PvM9949XDMZr8RUrGmxvlMSW3MhNAkjWSliwKqf2VV8z/Bildschirmfoto%202025-05-31%20um%2017.31.28.png)

*Fig.10: Overlay without scaling (black), with the same character widths (light grey) and filled with wider character variants (white) using the unitized method. As a result, you can see that the middle letters of the words remain in position and the spaces are reduced by the widened characters*



# Opentype Font

When extending the font, I started from our class first assignment practice font and made the following additions:

For the preliminary analysis, I defined 2 further variants within the font and assigned them to alternative letters grouped in the Opentype font to the CALT feature.



![Bildschirmfoto 2025-05-02 um 22.33.22.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/4d5d7c08-9783-a5a8-7802-c266707c2afb/9Tq6VNkebFGWHgNxyPBrHrn2TZjtS8z2GLzoJyIH4tsz/Bildschirmfoto%202025-05-02%20um%2022.33.22.png)

*Fig.11: One narrower and one wider version of the standard cut by one candence (1/4 stem width) each*



However, the use of the CALT feature turned out to be disadvantageous in the further course of the project, as it can only be set on the application side in Adobe InDesign® using complex click paths and also in the design and production process in Glyphs®, the assignment of character alternatives can only be done manually for each character and the character overview and selection quickly becomes confusing. That's why I decided to define the variants as variable axis wdth in the Opentype font. This means that all the parameters used in the normal section can be copied to the same font position and adapted for the axis position during design and production. The named fixed points of the axis can also be selected and assigned in the Indesign application as font style via the standard font menu without complex click paths.

At the beginning of the project, I used a total of 5 character alternatives from minus-2 to plus-2 cadences for the normal cut. Additional known targets were defined as references in the font for these axis positions.



![Bildschirmfoto 2025-05-31 um 17.10.01.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/E738D3DD-F76E-4819-8817-AE4456934FC3_2/YnA3GRtn90eEmAIVP9EicwbWz8wCq6bpuU0H9P0YqCsz/Bildschirmfoto%202025-05-31%20um%2017.10.01.png)

*Fig.12: Two variants of the standard cut, each narrower by 1/4 stem width and two wider*



- Capital letters were excluded: As the number of capital letters in continuous text is typically very low, the effects for the reduction of white space are below average. A deviation in letter width, on the other hand, is disproportionately noticeable. For this reason, only lowercase letters were taken into account by the function.
- Reduction to a maximum difference of one level: When checking the test results, however, it became clear that a deviation of 2 cadences quickly becomes noticeable, even for inexperienced readers, as soon as variants exceeding 1 cadence are used in the neighboring lines. In this respect, I have limited the application in the procedure described to 1 cadence.



![Bildschirmfoto 2025-05-03 um 09.11.23.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/5162824f-b88d-5ea0-acfe-d60797b23c56/x0nN30mt5t5X3dlmmoTQLveG4UoKeiGoYm7bthU3pusz/Bildschirmfoto%202025-05-03%20um%2009.11.23.png)

*Fig.13: Result with scaling to a maximum of 2 units shows conspicuous differences in width in the first, fifth and seventh lines of the paragraph (9 pt, Knuth-Plass-Justification, Unitized Scaling max. 2 units)*



![Bildschirmfoto 2025-05-03 um 09.12.07.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/9fd97fd5-eaee-aab1-588f-22780d45bce9/WHUO48JJXQjsbjszdNCRFQQ7a1P6be9yZQkf88gPziwz/Bildschirmfoto%202025-05-03%20um%2009.12.07.png)

*Fig.14: Result with scaling to a maximum of 1 unit shows hardly any differences in width, but still improved line formation due to a slight reduction in white space (9 pt, Knuth-Plass-Justification, Unitized Scaling max. 1 unit)*



![Bildschirmfoto 2025-05-03 um 09.11.36.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/7529ec2b-e600-1803-9850-ad65fedb8a2b/8aTPeb3HZu6ZeCDqI06th8fqsPxyTy1YXArGQfvFAgQz/Bildschirmfoto%202025-05-03%20um%2009.11.36.png)

*Fig.15: Result without scaling shows poorer line formation in the first and penultimate line due to the larger white space. (9 pt, Knuth-Plass-Justification, no scaling)*



- Discussion: This restriction naturally also has an influence on the reduction of the white space. For me, however, the positive effects of the restriction are the greater good to be preserved, since regardless of the scaling technique used, extremely short column widths would still result in oversized gaps that would render the scaling tool ineffective and counteract it with a new problem.
- Only pairs needed with one wider variant each: It also became clear that in the above procedure for reducing the whitespaces, only wider variants are required but no narrower ones. Reducing the width would only increase the whitespaces. In order to use the narrower variants, one could alternatively calculate with the narrow variants as a basic version, which are then extended with the normal version. I could imagine using them for bold headlines. In any case, this method only requires a second width for padding.



![Bildschirmfoto 2025-05-02 um 22.43.35.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/5ac115a1-3fc8-1a23-13b0-feedda03de6b/7F0gTlKnxdwE7jPv9ZMsIl6JDWYaXSsl0nKt45LxziMz/Bildschirmfoto%202025-05-02%20um%2022.43.35.png)

*Fig.16: The character set of the font used with additional variants of the lowercase letters, which are exactly one cadence wide.*



![Bildschirmfoto 2025-05-03 um 12.54.54.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/edc67dd9-5c90-fcc6-72d1-6384805a699c/trRKy0y0XjIKhWs412HMUIOUGD8TOlEj2kKaKvojC8Yz/Bildschirmfoto%202025-05-03%20um%2012.54.54.png)

![Bildschirmfoto 2025-05-03 um 12.57.49.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/5fd7eb43-ba46-14a7-2361-b09d8de44b45/jdG9P4JE0s0MKC7e2KiCIbEM4OLAYfdM2ExR7bxgq7Uz/Bildschirmfoto%202025-05-03%20um%2012.57.49.png)

*Fig.17: The glyphs are positioned exactly on the cadence grid. On the left the normal section with a stem interval of 14 cadences per 18 1/1000 EM (based on 1/4 stem width), on the right the wider version with a stem interval of 16 cadences. [Axis wdth=120]*



- It is precisely this process that was already used by Gutenberg, and although it can be automated using modern technology. (Although the abbreviations and certain ligatures are no longer comprehensible to the common reader today).
- Unitization is memory-friendly: In contrast to variable scaling, unitized scaling is much more memory-friendly, as the different variants are always stored as a separate font in conventional programs such as Indesign or storage formats such as PDF and the amount of memory increases significantly with the number of variants. In the test, I saw 8 times the amount of data for the same content.
- The angles of the italic fonts are retained: When using unitized scaling, the angles of the italic fonts are retained if they have been set up accordingly in the underlying font.



![Bildschirmfoto 2025-05-06 um 20.32.20.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/4620813c-1de6-562e-4874-c504a4538d63/NJJ0QjQLpq0jr5pJm86OZ6g5PhgwhJ5x1WI3VaD9SXoz/Bildschirmfoto%202025-05-06%20um%2020.32.20.png)

*Fig.18: Example of a test text in italic font.*



### Technical guidelines for compatible fonts

The font should be equipped with a wdth axis



![Bildschirmfoto 2025-05-06 um 20.47.48.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/201472bc-f5ee-896d-68c7-51e852b26faf/8U9bHRxVxpOeSAugQBj1BQ8ljN04e4SnAFs14Nq7Okoz/Bildschirmfoto%202025-05-06%20um%2020.47.48.png)

*Fig.19: The normal font is calibrated at 100, a wider variant at 120*



![Bildschirmfoto 2025-05-06 um 20.47.35.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/a119f7ad-6df2-21a1-fceb-908eba3830e4/rBPDOctftun7MwBSvBNiAjE4TJkG9ybmnyT4WAPiByIz/Bildschirmfoto%202025-05-06%20um%2020.47.35.png)

![Bildschirmfoto 2025-05-06 um 20.47.15.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/33c39111-a25f-41b8-886a-e17f1a852767/nzoXOA3ZFXMTnSxh1koEETytXRaIVwW6Z5qauGS40pwz/Bildschirmfoto%202025-05-06%20um%2020.47.15.png)

*Fig.20: The normal variant is placed on the unitized grid. The wide variant is extended by 2 units in the counter, and one unit is also added to the left and right on the outside*



![Bildschirmfoto 2025-05-06 um 20.54.05.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/d44a8a26-2a63-70e3-f4eb-f8addf13fee1/AzAVeCVqHLFpTBNoLmbMZ474DhYknQLLi4zxt4W1pHgz/Bildschirmfoto%202025-05-06%20um%2020.54.05.png)

![Bildschirmfoto 2025-05-06 um 20.53.52.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/fbe111c9-d6b1-5e53-cb94-6fe2efcfb216/9jUsaxBq7BakwWMytkwVbaZLjyCxrDbvuxPhtnYMRx0z/Bildschirmfoto%202025-05-06%20um%2020.53.52.png)

*Fig.21: Left the normal width n with 10 units in the counter, right the wide variant with 12 units in the counter*



As described above, however, the wide variant is to be classified as too wide when used. For this reason, only half the distance is used later for the unitized process instead of wdth=120, which then extends the counter by exactly one unit (wdth=110).



![Bildschirmfoto 2025-05-31 um 17.33.09.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/A1825A89-AB4A-40DF-8CA0-0C7FF644D9DE_2/VdMGwZDSJnObyqkHPv6ApKByANyBLd0JtFkn3nJxucwz/Bildschirmfoto%202025-05-31%20um%2017.33.09.png)

*Fig.22: Overview of font styles already available*



# Test samples

## Comparision no scaling vs. unitized scaling



[uni-none.html.pdf](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/E85E539E-EFDC-471E-A978-8214280CB6C5_2/nx4WHW8Y9obxRkDoqJyPYVEYZfHlT6hFT2Wb0FyxJiMz/uni-none.html.pdf)

*Attachment 3: Comparision none to unitized scaling results*



## Comparision traditional scaling vs. unitized scaling



[uni-trad.html.pdf](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/6718C5A3-9AC2-488D-9AA7-BECA88D19A4C_2/gUlpLOxRR2USDqURZK4ZYhQXLoJl9SLEjuPn5vJ9zRoz/uni-trad.html.pdf)

*Attachment 4: Comparision traditional to unitized scaling results*



# Evaluation

In the test installation, penalty values are determined for each paragraph based on the cumulative width of the additional spaces and displayed in the browser console. This was used to statistically evaluate and compare the results of the variants. The following diagrams show the penalty values for three different texts in a series of different sentence widths.

The following conclusions can be drawn from this:

- The smaller the column width, the more whitespace remains
- The results with unitized scaling are regularly better than without scaling
- When hyphenation is used, the results are better on average, but there are certain sentence widths where no improvement can be achieved for this sentence
- With hyphenation, the curves are more harmonious, the deviations at the transitions between sentence widths are then not so abruptly different
- The effect on white space reduction achieved by unitization is on average greater than that achieved by hyphenation.

### Example 1

„In olden times when wishing still helped one, there lived a king whose daughters were all beautiful; and the youngest was so beautiful that the sun itself, which has seen so much, was astonished whenever it shone in her face. Close by the king’s castle lay a great dark forest, and under an old lime-tree in the forest was a well, and when the day was very warm, the king’s child went out to the forest and sat down by the fountain; and when she was bored she took a golden ball, and threw it up on high and caught it; and this ball was her favorite plaything.“

111 words, 453 characters without spaces, 560 characters with spaces



![Image.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/716e526b-039b-8ef9-5317-59719fcedcfc/mij97xcyjhyPvHd9dx7Re6VppG5xl0xjAlx3GwqkYD0z/Image.png)

*Fig.23: Diagram for the text “In olden times ...” Penalty values (y-axis) for column widths from 192 to 576 pt (x-axis), red line = without scaling, blue line with unitized scaling, solid lines = with hyphenation, dashed = without hyphenation*



## Example 2

„Am Anfang war das Wort. Das Wort war bei Gott, und das Wort war Gott selbst. Von Anfang an war es bei Gott. Alles wurde durch das Wort geschaffen; nichts ist ohne das Wort entstanden. In ihm war das Leben, und dieses Leben war das Licht für alle Menschen. Es leuchtet in der Finsternis, und die Finsternis hat es nicht auslöschen können. Gott schickte einen Boten, einen Mann, der Johannes hieß. Sein Auftrag war es, die Menschen auf das Licht hinzuweisen. Alle sollten durch seine Botschaft an den glauben, der das Licht ist.“

93 words, 434 characters without spaces, 527 characters with spaces



![Image.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/59ee945a-4c1e-0533-9c70-07edd9329a51/leCcTGCfCqfm7nmSJxn1IjsuYfloIDk1J7Oc1VTOeZ4z/Image.png)

*Fig.24: Diagram for the text “In the beginning was ...” Penalty values (y-axis) for column widths from 192 to 576 pt (x-axis), red line = without scaling, blue line with unitized scaling, solid lines = with hyphenation, dashed = without hyphenation*



## Example 3

“By taking into account the classic design patterns of Latin typefaces, the rivers that occur when using justified text in narrow columns can be compensated for, creating a smoother more even composition and thus increasing the readability of the texts.”

40 words, 213 characters without spaces, 252 characters with spaces



![Image.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/a46b2d7d-f7b4-5443-3fc3-278949ab0bc6/vatUS79zn2OjDk0o0ePLijGsiPgNjQxnYhBlEZiKJagz/Image.png)

*Fig.25: Diagram for the text “By taking into ...” Penalty values (y-axis) for column widths from 192 to 576 pt (x-axis), red line = without scaling, blue line with unitized scaling, no values for hyphenation.*



# Practical use

I have made the fonts and functions available in a repository for integration into any application.

[https://github.com/jrgdrs/UniBaWiVa](https://github.com/jrgdrs/UniBaWiVa)

## Web pages HTML



![Bildschirmfoto 2025-05-06 um 20.23.50.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/080a3dc5-a11d-7be0-6677-b4f413cf4981/wjuxGOyLtqtLW5cbYTYFDjOGWT9GxZu7zu1qAbhyLB4z/Bildschirmfoto%202025-05-06%20um%2020.23.50.png)

*Fig.26: Example for the use of the function on websites*



I have prepared a polyfill for use on web pages. This allows functions that are not implemented by browsers to be added using JavaScript libraries if they are linked accordingly in the web pages. The polyfill expects the marking of the paragraphs with a freely definable selector and processes the break when the polyfill is executed at the end of the HTML document. The test examples above were created with the help of the polyfill.

## Adobe InDesign Plugin

I have prepared a plug-in for use in Adobe Indesign® that applies the selected optimization to the paragraphs after they have been marked. The plugin is still work in progress in an early stage.



![Bildschirmfoto 2025-05-31 um 17.35.15.png](https://res.craft.do/user/full/ce92c3bc-bf1f-2f0e-e611-560f02f61cc0/doc/37a2d212-9359-45ac-8a9b-ebdf231b405b/631914A8-08D9-4C20-A96D-7ABA81CA032B_2/WyEYWybLULcehjoQs88VaKCxY3nYyqCy1iHrF6r02N4z/Bildschirmfoto%202025-05-31%20um%2017.35.15.png)

*Fig.27: User interface of the Adobe Indesign PlugIn - work in progress*



----

# Jörg Drees

Born in 1967 on the German North Sea coast and was introduced to hot metal typesetting at an early age through his parents’ print shop. He later pursued his passion for letters and graduated as a typographic designer in Zurich, Switzerland.





