*Do you have JKI Simple Localization questions, ideas, or challenges you'd like discuss? Join the conversation happening in the [JKI Simple Localization Community Forum](https://forums.jki.net/forum/73-jki-simple-localization/).*

# JKI Simple Localization
A very simple LabVIEW toolkit for localizing VI front panels, based on a dictionary translation file.

This toolkit makes use of the "[Language for non-Unicode programs](https://www.digitalcitizen.life/changing-display-language-used-non-unicode-programs)" setting in Windows (located in the "Region and Language" settings). The toolkit uses a JSON dictionary file (can be in Unicode format) to store phrases in several different languages.  The toolkit will translate from the default language (typically English) to the target language specified as the "Language for non-Unicode programs" in Windows.

It does all this by making calls into the Windows API to translate the Unicode 16-bit characters from the dictionary into 8-bit non-unicode characters that can be displayed by non-Unicode program (assuming the "Language for non-Unicode programs" has been properly set in Windows).

In this way, LabVIEW developers have a simple way to localize their applications, even though LabVIEW does not support Unicode, out-of-the-box.

## Installation

You can download and install JKI Simple Localization with VI Package Manager.

[Get JKI Simple Localization](http://vipm.jki.net/package/jki_simple-localization)

### Requirements
- LabVIEW 2017 or greater
- Windows 7 or greater
- [VIPM 2017](https://vipm.jki.net) or greater

## Usage

*__IMPORTANT__: For this library to work, you must first set the "Language for non-Unicode Programs" to the target language you wish to translate into. [See instructions here](https://github.com/JKISoftware/JKI-Simple-Localization/wiki/Configuring-Windows-Language-(System-Locale))*

This library has just a handful of simple VIs required for use:

- Initialize - Loads a dictionary file.
- Set Language - Sets/changes the desired target language all registered VIs.
- Register VI - Registers a VI whose front panel will be localized to the target language any time Set Language is called.
- Set Language (By VI) - Sets/changes the desired target language of the VI without adding it to the registry.
- Get Localized Phrase - Allows translating a phrase from the default language to the target language, which is helpful for passing text in the default (programmers language) programmatically to dialogs (which should be displayed in the target/translated language).
- Get Languages - Gets all languages configured in the dictionary file.
- Generate Dictionary - Generates a dictionary file using the localizable text shown on the VIs in the current language. The file will need to be updated to include all additional languages.

*__NOTE__: This library uses key value pairs to localize phrases. By default, control and indicator __labels__ are used as the key to localize the __caption__, which should be shown instead of labels.*

### Palette

![SimpleLocalizationPalette](https://github.com/JKISoftware/JKI-Simple-Localization/blob/master/documentation%20support/Simple%20Localization%20Palette.png)

### Examples

See the Localization Demo VI on the *Functions >> JKI Tools >> JKI Simple Localization* palette.

![LocalizationDemoPalette](https://github.com/JKISoftware/JKI-Simple-Localization/blob/master/documentation%20support/Localization%20Demo%20Palette.png)

Run the VI and then choose a target language from the drop-down list.

__English__

![Example_english](https://github.com/JKISoftware/JKI-Simple-Localization/blob/master/documentation%20support/Example_english.png)

__Dutch__

![Example_dutch](https://github.com/JKISoftware/JKI-Simple-Localization/blob/master/documentation%20support/Example_dutch.png)

__Chinese__

![Example_chinese](https://github.com/JKISoftware/JKI-Simple-Localization/blob/master/documentation%20support/Example_chinese.png)

## Dictionary file

The dictionary file uses JSON format to list the languages, font information for each language, and key-value pairs linking each key to a set or localized phrases in each language in the dictionary.

[Example Dictionary File](https://github.com/JKISoftware/JKI-Simple-Localization/wiki/Example-Dictionary-File)

A formatted dictionary file can be generated from a VI front panel by going to Tools >> JKI Simple Localization Palette >> Localize This VI... *[See instructions here](https://github.com/JKISoftware/JKI-Simple-Localization/wiki/Generating-a-Localization-File-From-a-VI)*

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
