android-gradle-init-action
==========================
- [**Guide for getting a command line buildsystem for Android apps set up**](https://gist.github.com/stkptr/709d279212d4ee45133a8924724e2dc5)
- [How to create android project with gradle from command line? - Stack Overflow](https://stackoverflow.com/questions/20801042/how-to-create-android-project-with-gradle-from-command-line)
- [Scripts to create and maintain a kotlin project for Android without IDE (as in 2025)](https://gist.github.com/vokimon/38f1f6d2ce1b90bcb2676de2d51e520d)
- [AnandPilania/php-android-cli](https://github.com/AnandPilania/php-android-cli)

### Docs
- Build
  - https://developer.android.com/build
    - https://developer.android.com/build/building-cmdline#gradle_signing
    - https://developer.android.com/build/building-cmdline
- Structure
  - https://developer.android.com/build/android-build-structure
  - https://developer.android.com/build#settings-file
 
### Related
- https://github.com/gradle/declarative-gradle/tree/main/unified-prototype

### Init Scripts
- [ffgiff/gradle-init-scripts: Gradle init scripts/plug-ins adding checkstyle, findbugs, ktlint, pmd, sonar, doxygen, javadoc, pitest. Static checkers, documentation and mutation testing for arbitrary Android projects.](https://github.com/ffgiff/gradle-init-scripts/tree/master)

### [Gradle official template](https://docs.gradle.org/current/samples/sample_building_android_apps.html)
```
plugins {
    id("com.android.application") version "8.3.0"
}

repositories {
    google()
    mavenCentral()
}

android {
    compileSdk = 30
    defaultConfig {
        applicationId = "org.gradle.samples"
        namespace = "org.gradle.samples"
        minSdk = 16
        targetSdk = 30
        versionCode = 1
        versionName = "1.0"
        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }
    buildTypes {
        getByName("release") {
            isMinifyEnabled = false
            proguardFiles(getDefaultProguardFile("proguard-android-optimize.txt"), "proguard-rules.pro")
        }
    }
}

dependencies {
    implementation("androidx.appcompat:appcompat:1.2.0")
    implementation("com.google.android.material:material:1.2.0")
    implementation("androidx.constraintlayout:constraintlayout:2.0.4")
    testImplementation("junit:junit:4.13.1")
    androidTestImplementation("androidx.test.ext:junit:1.1.2")
    androidTestImplementation("androidx.test.espresso:espresso-core:3.3.0")
}
```
### Notes
- `android` cli was deprecated. It is only possible to init a gradle Android project from `gradle init` with hand-written file-replacement logic
