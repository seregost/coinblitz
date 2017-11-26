# CoinBlitz Mobile Bitcoin Wallet

[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/seregost/coinblitz/blob/master/LICENSE)

A mobile app geared towards use by the [`mylightning web wallet`](https://github.com/seregost/mylightning), but can be used with anything that supports the mylightning REST API specification.

## Installation

The following are rough instructions on how to install and test the application on an android device.

### 1. Preparing the project

To install the git workspace for this project type the following at a command line:

```
git clone https://github.com/seregost/coinblitz
cd coinblitz
```

### 2. Downloading PhoneGap CLI

Next you will need to install the latest version of the [`PhoneGap API`](https://phonegap.com/getstarted/) so that you can access the PhoneGap CLI.

### 3. Generating a Private Key

Next you will need to generate a keystore containing a private key with an alias corresponding to the name of the app.  In this case, the name is `com.seregost.coinblitz`.

As an example, refer to the [`first half of this guide.`](http://docs.phonegap.com/phonegap-build/signing/android/#generating-a-private-key)

This keystore will need to be placed in the root of the project folder and named `coinblitz.keystore`.  Please refer to [`build.json`](https://github.com/seregost/coinblitz/blob/master/build.json) for details on the script.

### 4. Building the project

You should now be ready to build the project.  In the project folder, type the following at the command line:

```
phonegap cordova prepare android
```

This will download the required plugins and prepare the android platform subfolder.

Once complete, type the following:

```
phonegap build android --release
```

This will build a signed release .apk file for the android platform.  It should ask you for the password for your keystore and private key created in `Step 3` above.

### 5. Install on device

If successful this build will create an `android-release.apk` file in the sub-directory `platforms/android/build/outputs/apk`.  This file can be copied to your android device and tested.
