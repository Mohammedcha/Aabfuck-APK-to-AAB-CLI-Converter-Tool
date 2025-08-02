# Documentation for aabfuck.exe

This document provides an overview and usage guide for the `aabfuck.exe` cli, a command-line tool designed to convert a standard Android `.apk` file into an Android App Bundle (`.aab`) format.

### 🔗 Download `aabfuck.exe`

**Link available in the Facebook group post.**  
⚠️ *You must be a member of the group to access the file.*

### Core Functionality

The `aabfuck.exe` cli automates the conversion of a compiled Android Application Package (`.apk`) into an Android App Bundle (`.aab`). It does this by leveraging a collection of external Android development tools. This process is crucial for developers who need to prepare their applications for distribution on modern platforms like the Google Play Store, which often requires the AAB format.

### Requirements

To run this tool successfully, you must have the following software and external tools installed and configured correctly. The cli expects all external tools to be located in a `tools` directory relative to the cli's location.

#### Software Dependencies

* **Java Runtime Environment (JRE):** The cli requires a version of Java 8.0.\* to be installed.

* **.NET Runtime:** The cli's help message indicates a requirement for .NET 7.0\*.

#### External Tools

The following external tools are required and should be placed in a `tools` directory within the project root.

| Tool | Purpose | Recommended Version |
 | ----- | ----- | ----- |
| `apktool.jar` | Decompiles APK files. | 2.5.0 |
| `aapt2` | Android Asset Packaging Tool for handling resources. | 2.20-eng.202508 |
| `android.jar` | Provides system resources and APIs from the Android framework. | android-30 |
| `bundletool.jar` | Generates and tests AABs from compiled resources. | 1.6.1 |

### Usage

The cli is executed via the command line and requires two essential arguments for input and output file paths.

#### Command-Line Arguments

* `-i` or `--input`: Specifies the path to the input APK file. This argument is **required**.

* `-o` or `--output`: Specifies the path for the output AAB file. This argument is **required**.

* `--apktool`: Optional. Path to `apktool.jar`. Defaults to `./tools/apktool.jar`.

* `--aapt2`: Optional. Path to `aapt2`. Defaults to `./tools/aapt2/{system}/aapt2`.

* `--android`: Optional. Path to `android.jar`. Defaults to `./tools/android.jar`.

* `--bundletool`: Optional. Path to `bundletool.jar`. Defaults to `./tools/bundletool.jar`.

#### Example

To run the cli, you would use a command similar to the following:

```
aabfuck.exe -i input.apk -o output.aab
```

### Troubleshooting and Version Compatibility

It is crucial to use the recommended tool versions to avoid potential errors. Using different versions, especially for a key tool like `bundletool`, can lead to unexpected errors or a failed conversion process.

