CSS Aural Properties

# CSS `Aural` Properties

Aural properties defines the aural rendering of a document.

## Aural Style Sheets

Aural style sheets are the part of CSS that uses a combination of speech synthesis and sound effects to make a web document more accessible to visually impaired and screen readers.

Aural presentation can be used:

*   by blind people
*   in the automobiles
*   in devices like home entertainment
*   industrial and medical documentation systems
*   to help users learning to read or who have difficulty reading

When using aural properties, the canvas consists of a three-dimensional physical space (sound surrounds) and a temporal space (one may specify sounds before, during, and after other sounds). The CSS properties also allow you to vary the quality of synthesized speech (voice type, frequency, inflection, etc.).

An example of an aural style sheet:

#### Example

*   `h1, h2, h3, h4, h5, h6 {`
*   `    voice-family: male;`
*   `    stress: 20;`
*   `    richness: 90;`
*   `    cue-before: url("pop.au");`
*   `}`
*   `p {`
*   `    azimuth: center-left;`
*   `}`
*   `quotes {`
*   `    volume: x-soft;`
*   `}`

This will direct the speech synthesizer to speak headers in a very rich male voice (a kind of "audio font").Before speaking the headers; a sound sample will be played from the given URL.

Paragraphs will appear to come from front left (if the sound system is capable of spatial audio). And quotes will be very soft.

| Property | Values | Description |
| --- | --- | --- |
| `azimuth` | _angle_  <br>`left-side`  <br>`far-left`  <br>`left`  <br>`center-left`  <br>`center`  <br>`center-right`  <br>`right`  <br>`far-right`  <br>`right-side`  <br>`behind`  <br>`leftwards`  <br>`rightwards`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Sets where the sound should come from horizontally. |
| `cue` | _cue-before_  <br>_cue-after_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Shorthand for setting the cue properties (i.e. cue-before and cue-after) in one declaration. |
| `cue-after` | `none`  <br>_url_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies a sound to be played after speaking an element's content to delimit it from other. |
| cue-before | `none`  <br>_url_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies a sound to be played before speaking an element's content to delimit it from other. |
| elevation | _angle_  <br>`below`  <br>`level`  <br>`above`  <br>`higher`  <br>`lower`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Sets where the sound should come from vertically. |
| `pause` | _pause-before_  <br>_pause-after_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Shorthand for setting the pause properties (i.e. pause-before and pause-after) in one declaration. |
| `pause-after` | _time_  <br>_%_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specify a pause to be observed after speaking an element's content. |
| `pause-before` | _time_  <br>_%_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specify a pause to be observed before speaking an element's content. |
| `pitch` | _frequency_  <br>`x-low`  <br>`low`  <br>`medium`  <br>`high`  <br>`x-high`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies the average pitch (a frequency) of the speaking voice. The average pitch of a voice depends on the voice family. |
| `pitch-range` | _number_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies variation in average pitch. |
| `play-during` | `auto`  <br>`none`  <br>`url`  <br>`mix`  <br>`repeat`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies a sound to be played as a background while an element's content is spoken. |
| `richness` | _number_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies the richness of the speaking voice. |
| `speak` | `normal`  <br>`none`  <br>`spell-out`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies whether text will be rendered aurally and if so, in what manner. |
| `speak-header` | `always`  <br>`once`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies whether table headers are spoken before every cell, or only before a cell when that cell is associated with a different header than the previous cell. |
| `speak-numeral` | `digits`  <br>`continuous`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies how numerals are spoken. |
| `speak-punctuation` | `none`  <br>`code`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies how punctuation characters are spoken. |
| `speech-rate` | _number_  <br>`x-slow`  <br>`slow`  <br>`medium`  <br>`fast`  <br>`x-fast`  <br>`faster`  <br>`slower`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies the speaking rate i.e. number of words spoken per minute. |
| `Stress` | _number_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies the "stress" in the speaking voice. |
| `voice-family` | _specific-voice_  <br>_generic-voice_  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies a comma-separated, prioritized list of voice family names. |
| `volume` | _number_  <br>_%_  <br>`silent`  <br>`x-soft`  <br>`soft`  <br>`medium`  <br>`loud`  <br>`x-loud`  <br>`[inherit](https://www.tutorialrepublic.com/css-reference/../definitions.php#inherit)` | Specifies the volume of the speaking voice. |
* * *