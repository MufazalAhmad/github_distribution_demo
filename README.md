1) Android
Run | Build

**To Run:**
1) Open the project folder in android studio.
2) Install flutter & dart plugins from plugins sections
3) Download flutter SDK version 3.13.3
   Download Flutter Link:
   https://docs.flutter.dev/release/archive?tab=macos
4) Set a flutter environment variable
   Flutter Env Variable (Windows):
   https://stackoverflow.com/questions/60212125/flutter-install-in-windows-environment-variable
   path of flutter in macos
   Flutter Path Variable (MacOS):
   https://rshankar.com/add-path-variable-in-macos-for-flutter/

5) Place upload-keystore.jks inside project/android/app and key.properties
   file inside project/android.
6) Open terminal:
   Run a command:
   `dart run build_runner build --delete-conflicting-outputs`
7) Run the following command to get SH256 key and SH1 key, copy both keys
   and into firebase:
   a) Open firebase
   b) open your project
   c) click android
   d) Add keys.
8) Open project again , attach android device in debug mode.
9) Run command to run the app:
   `flutter run --flavor=prod`

**To Build**
1) 1 to 6 repeat steps from to run section.
2) The upload-keystore.jks already given in folder, get SH256 & SH1 keys.
   SH Keys for and build:
   https://stackoverflow.com/questions/15727912/sha-1-fingerprint-of-keystore-certificate
   For release already added in firebase. For your system you need to just add.
   By following command:
   `keytool -list -v -keystore ~/.android/debug.keystore -alias 
   androiddebugkey -storepass android -keypass android`

3) Open pubspec.yaml file in project, increase the build number.
4) Open terminal and run following command to build installable android file
   apk.
   `flutter build apk --release --flavor=prod`
5) When the command running is completed, open 
   `project/build/outputs/flutter/app.release.apk` this is output file you need


**Ios Run**
1) Open project in android-studio
2) Delete `Project/pubspec.lock` if exit.
3) delete:
   `Project/ios/pods`
   `Project/ios/podfile.lock.`
   `Project/ios/symlinks`
4) Open the terminal run following command:
   `flutter clean`; 
   `flutter pub get`;
   `dart run build_runner build --delete-conflicting-outputs`; 
   `cd ios; pod install --repo-update`;
5) Click right on ios folder to bring folder options, in android-studio.
   Click the last option "Open in xcode".
6) Wait for indexing. Click the play button to run the app.

**Ios Build**
1) Change build number in pubspec.yaml file.
2) Run Ios, follow 1-5
3) Wait for indexing.
4) Select prod in top bar of Xcode.
5) Increment build number in xcode too.
6) Click product in the top bar.
7) Click archive and wait for archive is generated next validate and upload.



