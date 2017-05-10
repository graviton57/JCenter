# JCenter

### Uploading Android library to Jcenter gradle scripts. 
#### Library module build.gradle  
````gradle
apply plugin: 'com.android.library'
ext {
    bintrayRepo = 'maven'
    bintrayName = 'your_library_name'// Has to be same as your library module name
    publishedGroupId = 'com.github.your_github_login'
    libraryName = 'YourLibraryName' 
    artifact = 'your_library_name'  // Has to be same as your library module name
    libraryDescription = 'Your Library short description.'
    siteUrl = 'https://github.com/your_git_login/Your_repository'
    gitUrl = 'https://github.com/your_git_login/Your_repository.git'
    libraryVersion = '1.0.0'
    developerId = 'your_github_login'
    developerName = 'First Name Last Name'
    developerEmail = 'your@email.com'
    licenseName = 'The Apache Software License, Version 2.0'
    licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.txt'
    allLicenses = ["Apache-2.0"]
}

....

    //Add these lines to publish library to bintray
    //Place it at the end of the file
    apply from: 'https://raw.githubusercontent.com/graviton57/JCenter/master/installv1.gradle'
    apply from: 'https://raw.githubusercontent.com/graviton57/JCenter/master/bintrayv1.gradle'      
````  
  
#### Project build.gradle   

````gradle
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
         classpath 'com.android.tools.build:gradle:2.3.1'
         classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
         classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'
        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}  
````   

  
  
