


# Sass Gradle Compiler :zap:

A simple Sass compiler for gradle (tested only on Gradle 6.0+). Given a folder containing .sass and .css files, the plugin will compile them into a single file. 

> The plugin does not seem to work on a linux environment due to a dependency bug. For an alternative and for more information read [here](https://github.com/leobia/SassGradleCompiler/issues/1#issuecomment-1106609529)

## Instructions :pencil:

#### Import the plugin
Import the plugin using one of these:
```groovy
plugins {
  id "io.github.C0deMat.icentersassjavacompiler" version "0.3.0"
}
```

or using legacy plugin app:
```groovy
buildscript {
  repositories {
    maven {
      url "https://plugins.gradle.org/m2/"
    }
  }
  dependencies {
    classpath "gradle.plugin.io.github.C0deMat:icentersassjavacompiler:0.3.0"
  }
}

apply plugin: "io.github.C0deMat.icentersassjavacompiler"
```

#### Use the plugin
The usage of the plugin it's pretty simple, first you define the options (inside the *build.gradle*):

    sassOptions {  
      inputPath = file("./resources/")   
      outputPath = file("./resources/minified/")
      outputStyle = "compressed"  
      sass = true
      indentWithTabs = false
    }


|Option       |Type     |Description                                                             |
|-------------|---------|------------------------------------------------------------------------|
|inputPath*   |String   |It telss the plugin where to search input files (not recursive)         |
|outputPath   |String   |Directory where output should be saved (will be saved as *style.css*)   |
|sass         |Boolean  |Tells which files should be considered, **true** -> *.sass*, **false** -> *.scss*       |
|outputStyle  |String   |Possible values: *nested* (default), *compressed* (minified), *compact* and *expanded*    |

and then you can call the task:

    compileSass


## Built With :hammer:

* [Gradle](https://gradle.org/) - Dependency Management
* [jsass](https://jsass.readthedocs.io/en/latest/) - Used to compile sass

## Author :boy:

* **Leonardo Bianco** - [leobia](https://github.com/leobia)

Checkout my Gradle [JsCompiler](https://github.com/leobia/JsGradleCompiler) 

## License :page_facing_up:

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details

