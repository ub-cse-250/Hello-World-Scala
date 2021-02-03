# Hello-World-Scala
Use this repo to test that your IntelliJ setup is correct.

Please find the following information regarding setup of IntelliJ and getting started with Scala.

---

Installation/Setup
===

Install IntelliJ:
* You can use the JetBrains Toolbox to download and install IntelliJ for you: https://www.jetbrains.com/toolbox-app/
* You can download the install directly: https://www.jetbrains.com/idea/download/

Instructions for IntelliJ with Scala:
* https://docs.scala-lang.org/getting-started/intellij-track/getting-started-with-scala-in-intellij.html

Notes:
* You are welcome to configure the IDE as you wish, but please ensure that you do not disable Maven (enabled by default) when setting up your environment.
* We are using Scala 2.13 (which is also stated to be selected in the setup instructions).
* The exact version doesn't matter, so long as you use 2.13.XX (so 2.13.0, 2.13.4, etc. are OK).
* The version of JDK **does not matter**.

---

Setup ScalaTest
---

The `pom.xml` file distributed with our assignments will setup your project to automatically download the necessary dependencies to use ScalaTest.
When you want to create tests, create new Scala classes under the test directory (which should be marked as a Test Sources Root and will be colored green).
See ScalaTest tutorials:
* http://www.scalatest.org/user_guide
* http://scalatest.org/user_guide/selecting_a_style
* http://www.scalatest.org/user_guide/writing_your_first_test
* http://www.scalatest.org/user_guide/using_assertions
* and more on the ScalaTest site.

---

Test IntelliJ Setup
--- 

Download and run the HelloWorld project main and tests (contains the sample code from lecture covering Scala background).
1. Download zip file [Hello-World-Scala-main.zip](https://github.com/ub-cse-250/Hello-World-Scala/archive/main.zip) or clone Hello-World-Scala project [git@github.com:ub-cse-250/Hello-World-Scala.git](git@github.com:ub-cse-250/Hello-World-Scala.git)
    * You can find the repo at: https://github.com/ub-cse-250/Hello-World-Scala
2. Unzip/clone the files to somewhere you will remember.
3. Open IntelliJ. Click Open.
     * If a project is already open, go to `File > Open`.
4. Navigate to the folder you unzipped/cloned and select the folder `HelloWorld` and then click OK.
    * Note: if you clicked the folder *containing* HelloWorld and did not select the folder HelloWorld to open, you will need to go back to `File > Open` and try again.
5. Configure the **Sources Root** and **Test Sources Root** properties within your project.
    * Setup src directory: Right-click `src` folder > Mark Directory as > Sources Root.
    * Setup test directory: Right-click `test` folder > Mark Directory as > Test Sources Root.
6. In the Project view, go to `src > cse250.examples` and right-click HelloWorld.scala and select Run 'HelloWorld'
7. In the Project view, right-click `test` and select Run ScalaTests in 'test'...'

**Troubleshooting:**

Could not find or load main class.
> Error: Could not find or load main class cse250.examples.HelloWorld
> Caused by: java.lang.ClassNotFoundException: cse250.examples.HelloWorld

* You need to setup the Scala SDK for your project.
     1. Open `src/HelloWorld.scala`.
     1. Select Scala 2.13.XX from the menu. If not present, click Create > Download > Select the appropriate Scala version > Click OK > Click OK > Click OK.
     1. Try to run again.

ScalaTest cannot be found/loaded.
1. Right-click `pom.xml` and click "+ Add as Maven project" (at the bottom of the context menu).
      * If the "Maven" menu is already there, try to reimport the files "Maven > Reload Project."
      * If you disabled Maven (enabled by default setup), go to File > Settings > Plugins. Type `maven` into the search and click Enable. Click OK.


If it says `Project JDK undefined` at the top of HelloWorld.scala, click the button and select your JDK.

If it says `Maven projects need to be imported` click Import Changes.

Strange error that is verbose and makes no sense.
 * You may have updated the IntelliJ IDE but not the Scala plugin. Try to update the Scala plug and try again. To update:
       1. Open the File menu > Settings. Click the Plugins tab.
       1. Select Scala (make sure it is enabled, and if not enable it).
       1. Click to update, if the option is there. Click OK (and restart the IDE if necessary).

---

Q&A
---

1. What type of project will we use for Scala?
    * We will be working with IDEA projects. You may ignore any sbt instructions.
2. What if we already setup our environment using Scala 2.12, etc.?
    1. Update IntelliJ.
           * Go into `File -> Settings -> Appearance & Behavior -> System Updates -> Updates`. Versioning issues may arise if software is outdated. **Make sure you use the latest version** (at least 2019).
    2. Update your Scala Plugin
           * Go into `File -> Settings -> Plugins -> Update`. This is to get the most up to date version of scala in IntelliJ. You will need to restart the IDE after it has updated.
    3. Add Scala 2.13 SDK
           * Go to `File -> Project Structure -> Global Libraries -> + -> Scala SDK`. If Scala 2.13 is not present select the download button and it should appear. Click apply, then okay.
    4. Creating a new Scala Project
           * `File -> New -> Project -> Scala -> IDE`. Make sure that Scala 2.13 is showing up for the Scala SDK.
    5. Once Scala 2.13 does show up, make sure to remove Scala 2.12 from your global libraries
3. Why isn't my `import` statement working?
    * Scala, unlike Java, doesn't care about file directory for package structure (or for that matter, it also doesn't care about the class name being the same as the filename). In order to put source files into a package, simply put the package name at the top of the file in a package declaration. E.g.,
           
           package cse250.examples
           
           class MyNewClass {
           ???
           }
      puts the class `MyNewClass` inside the package `cse250.examples`. To access this class externally, you can either use `import cse250.examples.MyNewClass` to access `MyNewClass` without any qualifiers, or import the entire `cse250.examples` package and then reference the class via `examples.MyNewClass`.
4. ... more to come as questions arise.

---

Additional Resources:
---

* http://allaboutscala.com/tutorials/chapter-1-getting-familiar-intellij-ide/

