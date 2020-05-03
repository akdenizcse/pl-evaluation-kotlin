# Kotlin Programming Language Evaluation

![drawing](https://www.sngular.com/wp-content/uploads/2019/11/Kotlin-Blog.png)

## 1)   History of the Language: Who/When Invented, Which Languages Influenced It, etc.

Kotlin is a free, open-source and strong statically typed object-oriented programming language. Kotlin is published as a new language for the JVM, Android, JavaScript and Native, which had been under development for a year in July 2011 by JetBrains with lead language designer is Andrey Breslav. The first version Kotlin v1.0 was released on February 15, 2016, which can be considered the first official stable version. Google Announced First-class Support For Kotlin On Android At Google I/O in 2017. It has been open source since 2012. It looks like a more concise and streamlined version of Java. It is developed under the Apache 2.0 license, and the source code is accessible on GitHub. Since it is open-source, there are more than 250 external contributors on GitHub. Kotlin can be used for android development, server-side development, web development, desktop development, native development and so on.  Kotlin is influenced by Java, C#, JavaScript, Scala and Groovy. 

## 2)   Why Was It Invented?

Kotlin was invented to help the developers' problems of the JetBrains. The more straightforward tool was needed than Java to work in IntelliJ IDEA. While the alternative of Java-like languages did not become efficient enough, then they invented Kotlin. It was essential to work with any platform that Java works especially Android app development. Kotlin improves Java's weaknesses in every way to code it adequately and more rigid. 


## 3)   When/Why Shall We Use It?

Kotlin is a more concise and has a streamlined version of Java and has simpler syntax and therefore easier to learn.  It can be used whether on Desktop apps, Mobile apps, Web apps etc. Rough estimation indicates that using Kotlin permits you to remove the lines of code by around 40% (contrasted with Java). Kotlin allows developers to declare the functions at the top level. Kotlin does not have regular static handling modifier like Java, which can make some issues the regular Java designers. Strong type inference is one reason. Java has consistently been known for its verbosity. Kotlin permits us to expand the use of existing classes without inheriting from them. It is aimed at removing the dangers of null references from the code. Kotlin can interoperate with approximately composed situations, for example, such as the JavaScript ecosystem, be that as it may, it is a statically typed language. Subsequently, the type checking occurs at compile-time as opposed to run-time, and minor bugs are gotten at a beginning time. It has "Null pointer exception" in compilation-time instead of run-time.  It allows developers to solve the problem before proceeding. With Kotlin's help for inline functions, code regularly runs quicker. Returned values can be unpacked into separate variables using destructuring declaration. Many asynchronous mechanisms available in other languages can be implemented as libraries using Kotlin coroutines. This includes async/await from C# and ECMAScript, channels and select from Go and generators/yield from C# and Python. Furthermore, similar to C#, in Kotlin you can define methods on a class while not writing them inside the class 

## 4)   How to Setup an Environment to Use In Different Platforms?

Using Kotlin for Desktop or Android Development, both IntelliJ IDEA and Android Studio work which are the products of JetBrains itself can be used in macOS, Windows and Linux. Coding in those IDEs is easy to implement Kotlin. Creating a project with Kotlin will just work fine. Then you start coding if you installed the required versions of JDK or SDK depends on the platform. In server-side development, frameworks like Spring, Vert.x, Ktor, Kotlinx.html etc. can be used.
Kotlin has multi-platform support, which infers that code can be reused across Android, iOS or Web. Kotlin runs on JVM. Subsequently, it is essential to use the latest version of JDK for your local Kotlin development. Intellij, Eclipse and NetBeans are the most used IDEs for Kotlin development. However, since it is released by JetBrains, IntelliJ IDEA will be the most suitable IDE to work with. As a desktop development, JavaFx, Swing, TornadoFX and other tools can be integrated to Kotlin. Also, it has the ability to target JavaScript. Its implementation targets ECMAScript 5.1. This is how Kotlin can be used in web development:

*   Interacting with DOM elements: Kotlin provides a series of statically typed interfaces to interact with the Document Object Model, allowing creation and update of DOM elements.
*   Interacting with graphics such as WebGL. You can use Kotlin to create graphical elements on a web page using WebGL.
*   You can use Kotlin to interact with server-side JavaScript such as Node.js. In addition to that, several third-party libraries and frameworks, such as Spring, Vert.x, Ktor, kotlinx.html, Micronaut,  Javalin, jQuery, React, and Corda can be used.

To work on web development, creating a new project choosing in Gradle / Kotlin / JS for browser, node.js etc. is enough. 

As a result, those are implemented in the root of app build.grade.kts

```
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
```
For developing a cross-platform library in Kotlin is to create a new multi-platform project. To do this, IntelliJ IDEA is again used. One example repo can be found here:
https://github.com/MrAsterisco/KotlinMultiPlatformPlayground
The default configuration creates three modules and a test module for each, with a total of six modules:
commonMain: This module contains all the common rationale written in Kotlin. Any class in here can be shared across any platform.
iosMain: a module that interfaces the Cocoa framework and permits us to write Kotlin code which will take a shot at iOS in particular. 
jvmMain: a module that compiles to Kotlin/JVM and links the Android system. This will work on Android only. As a result, those are implemented in the root of app build.grade.kts:

```
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
```
Use an online compiler, for example, https://play.kotlinlang.org/ 
No need to download and install. Still require an IDE for class project on a personal computer
https://try.kotlinlang.org/#/Examples/Hello,%20world!/Simplest%20version/Simplest%20version.k

## 5)   Example Codes
-------------------------------------------------------------------------------------------------

> Basic print function
```
fun main() {
    println("Hello, World!")
} 
```

 -------------------------------------------------------------------------------------------------
> Function that returns an integer
```
fun sum(x: Int, y: Int): Int {
    return x – y
}
```

 -------------------------------------------------------------------------------------------------
> Single-expression function: integer return is inferred
```
fun multiply(x: Int, y: Int) = x / y
```

 -------------------------------------------------------------------------------------------------
> Concatenation
```
val name = "Sam" 
val str = "hello $name" 
val str = "hello $name. Your name has ${name.length} characters"
```

 -------------------------------------------------------------------------------------------------
> Use val for immutability
```
var a: String = "first"
val b: Int = 1
```

 -------------------------------------------------------------------------------------------------
> Null safety
```
var neverNull: String = "Not null string"
neverNull = null // this results in a compiler error
var nullable: String? = "Keep null string"
nullable = null // no error here
```

 -------------------------------------------------------------------------------------------------
> Use of classes
```
class Customer
class Contact(val id: Int, var email: String)
fun main() {
    val customer = Customer()
    val contact = Contact(1, "a@mail.com")
    println(contact.id)
    contact.email = "b@gmail.com"
}
```

 -------------------------------------------------------------------------------------------------
> Inheritance: use open to allow inheritance
```
open class Tiger(val origin: String) {
    fun roar() {
        println("A tiger from $origin says: grrhhh!")
    }
}
```
```
class SiberianTiger : Tiger("Siberia")
fun main() {
    val tiger: Tiger = SiberianTiger()
    tiger.roar()
}
```

 -------------------------------------------------------------------------------------------------
> for loop
```
val cakes = listOf("strawberry", "chocolate", "milk")
for (cake in cakes) {
    println("Mmmh, it's a $cake cake!")
}
```

 ------------------------------------------------------------------------------------------------- 
> for loop based on range
```
for(i in 2..100 step 2) {
    print(i)
}
```

 ------------------------------------------------------------------------------------------------- 

> Multiple Return 
```
fun positiveRoot(k: Int): Double { 
    require(k >= 0) 
    return Math.sqrt(k.toDouble()) 
} 
```
```
fun negativeRoot(k: Int): Double { 
    require(k >= 0) 
    return -Math.sqrt(k.toDouble()) 
} 
```
```
fun roots(k: Int): Array { 
    require(k >= 0) 
    val root = Math.sqrt(k.toDouble()) 
    return arrayOf(root, -root) 
} 
```
```
class Roots(pos: Double, neg: Double) 
fun roots2(k: Int): Roots { 
    require(k >= 0) 
    val root = Math.sqrt(k.toDouble()) 
    return Roots(root, -root) 
} 
fun roots3(k: Int): Pair <Double, Double> { 
    require(k >= 0) 
    val root = Math.sqrt(k.toDouble()) 
    return Pair(root, -root) 
}
```

 -------------------------------------------------------------------------------------------------
 
> Android change activity
```
private fun switchToMap() { 
val intent = Intent(this, MapsActivity::class.java) 
startActivity(intent) 
}
```

> Reified Types

```
inline fun <reified T : Activity> Context.open() = startActivity(Intent(this, T::class.java))
inline fun <reified T : Activity> Context.openForResult(code: Int) = startActivityForResult(Intent(this, T::class.java), code)
inline fun <reified T : Fragment> newInstance(): T = T::class.java.newInstance()

Usage: 

open<LoginActivity>()

openForResult<LoginActivity>(INTENT_CODE)

supportFragmentManager
    .beginTransaction()
    .replace(R.id.login_fragment_container, newInstance<LoginFragment>())
    .commit()
```

> Apply Function
```
val zaphod = Person().apply {
  firstName = "Zaphod"
  lastName = "Beeblebrox"
  headCount = 2
}
```

> Single Expression Function
```
fun fullName() = firstName + " " + lastName
```

> Higher Order Function
```
	// lambda expression 
var lambda = {a: Int , b: Int -> a + b } 
	// higher order function 
fun higherfunc( lmbd: (Int, Int) -> Int) {	 // accepting lambda as parameter 
		
	var result = lmbd(2,4) // invokes the lambda expression by passing parameters					 
	println("The sum of two numbers is: $result") 
} 

fun main(args: Array<String>) { 
	higherfunc(lambda)		 //passing lambda as parameter 
}
```

 -------------------------------------------------------------------------------------------------

## 6)   Things Those Are Specific to This Language

The development of Kotlin is aimed at eliminating the danger of null references from code. Kotlin uses data binding to link XML variables to Kotlin values using the Kotlin Android Extensions framework. Data binding reduces run-time lookup of XML variable via findViewById(), and thus a potential source of run-time errors. Therefore, we can say that null safety is the primary benefit of Kotlin. Furthermore, allowing developers to use lambda expressions(also valid in Java) and inline functions with functions generate multiple return values makes a great benefit.
