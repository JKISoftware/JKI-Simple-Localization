# JKI Simple Localization
A very simple LabVIEW toolkit for localizing VI front panels

This library uses a Dictionary file which maps the captions of font panel items to a language at runtime. You can use this to dynamically update your front panel to display different languages.

## Installation

You can download and install JKI Simple Localization with VI Package Manager.

[Get JKI Simple Localization](http://vipm.jki.net/#!/package/jki_lib_simple-localization)

## Usage
This library uses your custom Dictionary to map the displayed **captions** of front panel items to a desired language.

It is important to note that LabVIEW cannot update controls' labels at runtime, so this library updates the **captions**, which must be intentionally displayed (the default behavior is to display the control's label)

**Dictionary Formatting:**

The first line defines which languages are being used: "UID|Language1|Language2|..LanguageN"

Subsequent lines define the map: "Unique Control Name/Label|Language1 Representation|Language2 Representation"

The library currently supports setting a font name and color based on language: "\_\_Font.Name\_\_|lang1 font name|lang2 font name", "\_\_Font.Color\_\_|lang1 font color|lang2 font color" where font color is a U32.


**ReadDictionary.vi:**

This will read your Dictionary file and create a 2D array that is used to map controls' captions.


**TrasnslateVI.vi:**

Given the Dictionary created in ReadDictionary, a reference to the VI to be translated, and a language, this will update the front panel controls and indicators based on your Dictionary.


**TranslationFGV.vi:**

This combines the two functions above, storing the Dictionary in the shift register so that the user does not need to pass around the Dictionary structure.

**Get Windows Primary Language.vi**

Use this VI to programatically determine the primary language used by the machine.

**Class Specific:**

The library may also read properties of specific class items by adding lines in the Dictionary which append keywords based on the control type:

GraphOrChart, WaveformChart, WaveformGraph, XYGraph: (.xAxisLabel, .yAxisLabel)

Boolean (Boolean Text: False, True)

Ring (.Item0, Item1.. ItemN)

Here is an example of a dictionary item to set the boolean text:

`UID|English|French`

`MyBool|Pump|Pompe`

`MyBool.True|Vent|Vent`

`MyBool.False|Vacuum|Vide`

To add specific controls that are not currently supported, update the case structure of SetClassSpecific.vi to include a case for the desired "ClassName". You can add suffixes to controls in the dictionary to access other parameters (ex: .xAxisLabel, .False).

### Palette

{documentation}

### Examples
You can find examples on how to use the Simple Localization library under the LabVIEW examples directory

`<LabVIEW>\examples\JKI Toolkits\JKI Simple Localization`

## Support

If you encounter incorrect or undocumented behavior or would like to file a new feature request, you can do so by filing a new issue on
[GitHub](https://github.com/JKISoftware/JKI-Simple-Localization/issues). For paid customized support, please contact [JKI](http://jki.net).

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

To contribute to JKI Simple Localization, you will need 32-bit LabVIEW 2017 professional development environment.

## Credits

JKI Simple Localization is an open source project maintained by [JKI](http://jki.net).

## License

JKI Simple Localization is distributed under the open source three clause BSD license providing everyone right to use and distribute both souce code and compiled versions of the software. See LICENSE.md file for details.
