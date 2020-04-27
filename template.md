ProgLangName

- History of the language: who/when invented it, which languages influenced it, etc.

Kotlin is a free, open-source and strong statically typed object-oriented programming language. Kotlin is published as a new language for the JVM, Android, JavaScript and Native, which had been under development for a year in July 2011 by JetBrains with lead language designer is Andrey Breslav. The first version Kotlin v1.0 was released on February 15, 2016, which can be considered the first official stable version. Google Announced First-class Support For Kotlin On Android At Google I/O in 2017. It has been open source since 2012. It looks like a more concise and streamlined version of Java. It is developed under the Apache 2.0 license, and the source code is accessible on GitHub. Since it is open-source, there are more than 250 external contributors on GitHub. Kotlin can be used for android development, server-side development, web development, desktop development, native development and so on.  Kotlin is influenced by Java, C#, JavaScript, Scala and Groovy. 

- Why was it invented
- When/why shall we use it

Kotlin is a more concise and has a streamlined version of Java and has simpler syntax and therefore easier to learn.  It can be used whether on Desktop apps, Mobile apps, Web apps etc. Rough estimation indicates that using Kotlin permits you to remove the lines of code by around 40% (contrasted with Java). Kotlin allows developers to declare the functions at the top level. Kotlin does not have regular static handling modifier like Java, which can make some issues the regular Java designers. Strong type inference is one reason. Java has consistently been known for its verbosity. Kotlin permits us to expand the use of existing classes without inheriting from them. It is aimed at removing the dangers of null references from the code. Kotlin can interoperate with approximately composed situations, for example, such as the JavaScript ecosystem, be that as it may, it is a statically typed language. Subsequently, the type checking occurs at compile-time as opposed to run-time, and minor bugs are gotten at a beginning time. It has "Null pointer exception" in compilation-time instead of run-time.  It allows developers to solve the problem before proceeding. With Kotlin's help for inline functions, code regularly runs quicker. Returned values can be unpacked into separate variables using destructuring declaration. Many asynchronous mechanisms available in other languages can be implemented as libraries using Kotlin coroutines. This includes async/await from C# and ECMAScript, channels and select from Go and generators/yield from C# and Python. Furthermore, similar to C#, in Kotlin you can define methods on a class while not writing them inside the class 

- How to setup an environment to use it in different platforms

Using Kotlin for Desktop or Android Development, both IntelliJ IDEA and Android Studio work which are the products of JetBrains itself can be used in macOS, Windows and Linux. Coding in those IDEs is easy to implement Kotlin. Creating a project with Kotlin will just work fine. Then you start coding if you installed the required versions of JDK or SDK depends on the platform. In server-side development, frameworks like Spring, Vert.x, Ktor, Kotlinx.html etc. can be used.
Kotlin has multi-platform support, which infers that code can be reused across Android, iOS or Web. Kotlin runs on JVM. Subsequently, it is essential to use the latest version of JDK for your local Kotlin development. Intellij, Eclipse and NetBeans are the most used IDEs for Kotlin development. However, since it is released by JetBrains, IntelliJ IDEA will be the most suitable IDE to work with. As a desktop development, JavaFx, Swing, TornadoFX and other tools can be integrated to Kotlin. Also, it has the ability to target JavaScript. Its implementation targets ECMAScript 5.1. This is how Kotlin can be used in web development:

Interacting with DOM elements: Kotlin provides a series of statically typed interfaces to interact with the Document Object Model, allowing creation and update of DOM elements.
Interacting with graphics such as WebGL. You can use Kotlin to create graphical elements on a web page using WebGL.
You can use Kotlin to interact with server-side JavaScript such as Node.js. In addition to that, several third-party libraries and frameworks, such as Spring, Vert.x, Ktor, kotlinx.html, Micronaut,  Javalin, jQuery, React, and Corda can be used.

To work on web development, creating a new project choosing in Gradle / Kotlin / JS for browser, node.js etc. is enough. 




As a result, those are implemented in the root of app build.grade.kts

plugins {
    id("org.jetbrains.kotlin.js") version "1.3.70"
}
group = "org.example"
version = "1.0-SNAPSHOT"
repositories {
    mavenCentral()
}
dependencies {
    implementation(kotlin("stdlib-js"))
}
kotlin.target.browser { } 

For developing a cross-platform library in Kotlin is to create a new multi-platform project. To do this, IntelliJ IDEA is again used. One example repo can be found here:
https://github.com/MrAsterisco/KotlinMultiPlatformPlayground
The default configuration creates three modules and a test module for each, with a total of six modules:
commonMain: This module contains all the common rationale written in Kotlin. Any class in here can be shared across any platform.
iosMain: a module that interfaces the Cocoa framework and permits us to write Kotlin code which will take a shot at iOS in particular. 
jvmMain: a module that compiles to Kotlin/JVM and links the Android system. This will work on Android only. As a result, those are implemented in the root of app build.grade.kts:

plugins {
    kotlin("multiplatform") version "1.3.70"
}
group = "org.example"
version = "1.0-SNAPSHOT"
repositories {
    mavenCentral()
}
kotlin {
    js {
        browser { }
    }

    sourceSets {
        val commonMain by getting {
            dependencies {
                implementation(kotlin("stdlib-common"))
            }
        }
        val commonTest by getting {
            dependencies {
                implementation(kotlin("test-common"))
                implementation(kotlin("test-annotations-common"))
            }
        }

        val jsMain by getting {
            dependencies {
                implementation(kotlin("stdlib-js"))
            }
        }
        val jsTest by getting {
            dependencies {
                implementation(kotlin("test-js"))
            }
        }
    }
}
Use an online compiler, for example, https://play.kotlinlang.org/ 
No need to download and install. Still require an IDE for class project on a personal computer
https://try.kotlinlang.org/#/Examples/Hello,%20world!/Simplest%20version/Simplest%20version.k


- Example codes
- Things that are specific to this language?
