# intune-uploader

## Description
This project aims to simplify the process of creating and updating apps and other payloads in Intune by leveraging the power of [AutoPkg](https://github.com/autopkg/autopkg). With AutoPkg, you can automate the process of downloading, packaging, and uploading apps to Intune, saving you time and effort.

Moving forward, additional processors for Intune might be added to this project that uploads more data like Shell scripts to provide a complete automated deployment process. This is why the base class [IntuneUploaderBase](IntuneUploader/IntuneUploaderLib/IntuneUploaderBase.py) was created, to allow for easier creation of additional processors. Contributions are welcome!

Ideas for future processors:
- Teams notifier processor
- App promoter

For getting started help and documentation, please visit the wiki pages:
- [Intune App Uploader](https://github.com/almenscorner/intune-uploader/wiki/IntuneAppUploader)
- [Intune App Icon Getter](https://github.com/almenscorner/intune-uploader/wiki/IntuneAppIconGetter)
- [Intune App Cleaner](https://github.com/almenscorner/intune-uploader/wiki/IntuneAppCleaner)
- [Intune Script Uploader](https://github.com/almenscorner/intune-uploader/wiki/IntuneScriptUploader)

### IntuneAppUploader - LOB apps (managed PKG)
LOB type apps support has been added. It is required that you provide a pkg file that is signed with a valid Apple Developer ID certificate and notarized. This app type can be deploy apps in a "available" manner rather than "required". This means that the user can choose to install the app or not. This is useful for apps that are not required for the user to do their job, but are nice to have.

In the override file for a signed and notarized pkg, set the following key to upload as a LOB app:
```xml
<key>lob_app</key>
<true/>
```