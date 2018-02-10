# JKI Simple Localization
A very simple LabVIEW toolkit for localizing VI front panels, based on a dictionary translation file.

This toolkit makes use of the "[Language for non-Unicode programs](https://www.digitalcitizen.life/changing-display-language-used-non-unicode-programs)" setting in Windows (located in the "Region and Language" settings). The toolkit uses a plaintext dictionary file (can be in Unicode format) to store phrases in several different languages.  The toolkit will translate from the default language (typically English) to the target language specified as the "Language for non-Unicode programs" in Windows.

It does all this by making calls into the Windows API to translate the Unicode 16-bit characters from the dictionary into 8-bit non-unicode characters that can be displayed by non-Unicode programe (assuming the "Language for non-Unicode programs" has been properly set in Windows).

In this way, LabVIEW developers have a simple way to localize their applications, even though LabVIEW does not support Unicode, out-of-the-box.

## Installation

You can download and install JKI Simple Localization with VI Package Manager.

[Get JKI Simple Localization](http://vipm.jki.net/#!/package/jki_lib_simple-localization)

### Requirements
- LabVIEW 2017 or greater
- Windows 7 or greater
- [VIPM 2017](https://vipm.jki.net) or greater

## Usage

*__IMPORTANT__: For this library to work, you must first set the "Language for non-Unicode Programs" to the target language you wish to translate into. [See instructions here](https://github.com/JKISoftware/JKI-Simple-Localization/wiki/Configuring-Windows-Language-(System-Locale))*

This library has just a few simple VIs that are required for use:

- Initialize - Loads a dictionary file
- Set Language - Sets/changes the desired target language
- Register VI - Registers a VI who's front panel will be translated to the target language

### Palette

![2018-02-09_20-19-26](https://user-images.githubusercontent.com/381432/36058495-8ac46168-0dd6-11e8-8749-be8b7c416222.png)

### Examples

See the Localization Demo VI on the *Functions >> JKI Tools >> JKI Simple Localization* palette.

Run the VI and then choose a target language from the drop-down list.

__English__

![2018-02-09_20-25-27](https://user-images.githubusercontent.com/381432/36058515-61539302-0dd7-11e8-886c-cb0b1eb9592a.png)

__Chinese__

![2018-02-09_20-25-42](https://user-images.githubusercontent.com/381432/36058517-6aaadf8c-0dd7-11e8-9a34-486cab52e7cd.png)


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
