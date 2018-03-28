<p align="center">
  <a href="http://mobbeel.com">
    <img src="http://www.mobbeel.com/wp-content/uploads/2015/03/mobbeel_logo_transparente.png" width="350px">
  </a>
  <center><font size="5">Mobbeel fat AAR Gradle plugin</p></center>
</p>

[<img src="https://img.shields.io/hexpm/l/plug.svg">](https://raw.githubusercontent.com/Mobbeel/fataar-gradle-plugin/master/LICENSE)

In [Mobbeel](http://www.mobbeel.com/) we work with a complex hierarchy of modules that in turn must embed other dependencies in the resulting AAR. To do this we use this Gradle plugin that allows to merge a project and its dependencies in the same AAR (fat-aar).

Issue reporting are welcome to continue to improve this plugin.

> Plugin work with Android gradle plugin 3.0.0 o higher

### How to use?

1. Configure your buildscript to include the plugin:

  ```
  buildscript {
    repositories {
      maven { url "https://plugins.gradle.org/m2/" }
    }
    dependencies {
      classpath "gradle.plugin.com.mobbeel.plugin:mobbeel-fataar:1.0.0"
    }
  }
  ```

2. Apply the plugin on the top of your library module **build.gradle**:

  ```
  apply plugin: "com.mobbeel.plugin"
  ```

3. Mark with '**api**' configuration dependecies that need embed on the final AAR:

  ```
  dependencies {
      api "com.mobbeel:my-lib:1.0.0"  // <- Embed external dependency from any repository
      api project(':My-lib-module')   // <- Embed internal dependency on workspace

      ...
  }
  ```
