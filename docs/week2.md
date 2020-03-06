# Java Project: Week 1

In dit project werken we aan de **Java** opdracht. Hierin werken we aan:
 * ~~Gradle en Java~~
 * Code Analyse
 * ~~Multi-module projecten~~
 
## Inhoudsopgave
 T.B.A.
 
## Checking	coding	standards	with	Checkstyle
 
#### 1. Go to the Checkstyle plugin page and apply the plugin

build.grade
```groovy
plugins {
    // Checkstyle plugin https://docs.gradle.org/current/userguide/checkstyle_plugin.html
    id 'checkstyle'
}
```

#### 2. Create a basic Checkstyle configuration file (or get the Google version online!) and place it in the default location

I got the Google version from [here](https://raw.githubusercontent.com/checkstyle/checkstyle/master/src/main/resources/google_checks.xml)

```
BookCase-Gradle
├───config
│   └───checkstyle
│           checkstyle.xml
```

#### 3. After your configuration file is in place, make sure to test your configuration by running the appropriate task and take a look at the results

Running `gradle check`

**Artefacts**

```
build
└──reports
   └────checkstyle
          main.html
          main.xml
          test.html
          test.xml
```

#### 4. What Java plugin tasks gets an additional dependency thanks to the Checkstyle plugin?
Dat is de `check` task. Die runt nu ook de checkstyle

#### 5. Design a Checkstyle configuration document based on existing Checkstyle modules in which you check that your project adheres to at least ten (10) coding standards of your choosing.

| Module                                 | Description
| :------------------------------------  | :---------------------------------------------
| EmptyBlock                             | Checks for empty blocks.
| AvoidStarImport                        | Checks that there are no import statements that use the * notation.
| MethodLength                           | Checks for long methods and constructors.
| OneTopLevelClass                       | Checks that each top-level class, interface or enum resides in a source file of its own.
| OverloadMethodsDeclarationOrder        | Checks that overload methods are grouped together.
| SimplifyBooleanReturn                  | Checks for over-complicated boolean expressions.
| SimplifyBooleanExpression              | Checks for over-complicated boolean return statements.
| TodoComment                            | Checks for TODO: comments.
| UnusedImports                          | Checks for unused import statements.
| MissingSwitchDefault                   | Checks that switch statement has a default clause.


#### 6. [Deliverable] Create a document that explains your own coding standard. You do not need to copy your configuration (you can just submit the XML), but we would like to see "some" reasoning on why you chose the checks you have opted for. You'll submit this document as part of your first turn-in in the upcoming weeks

| Module                                 | Redenering
| :------------------------------------  | :---------------------------------------------
| EmptyBlock                             | Ik wil geen onnodige dingen in de code. Dat zal ook gelden voor veel andere dingen in deze tabel.
| AvoidStarImport                        | Het staat netter, gebruikt minder ruimte en is nog sneller ook
| MethodLength                           | Lange methodes maken je code onleesbaar. Het is beter om ze op te delen
| OneTopLevelClass                       | Elke class moet zijn eigen file hebben. Anders raak je het overzicht kwijt.
| OverloadMethodsDeclarationOrder        | Als je methodes overload, zorg dan dat ze dichtbij elkaar staan, anders raak je het overzicht kwijt
| SimplifyBooleanReturn                  | Zodat je snel door de code kan lezen zonder een return te ontcijferen
| SimplifyBooleanExpression              | Zelfde als SimplifyBooleanReturn. Verbeterd de leesbaarheid
| TodoComment                            | Als een TODO klaar is, haal de comment dan weg...
| UnusedImports                          | Zelfde als StarImport. Het is niet nodig, kost ruimte en maakt het programma langzamer
| MissingSwitchDefault                   | Ik vergeet deze nog wel eens. Dus als reminder!

## Finding bugs with SpotBugs

#### 1. Look at SpotBugs documentation: how many detectors are there and what are they looking for? 
>SpotBugs checks for more than 400 bug patterns.

Ze zoeken naar:
 * Bad practice
 * Correctness
 * Experimental
 * Internationalization
 * Malicious code vulnerability
 * Multithreaded correctness
 * Bogus random noise
 * Performance
 * Security
 * Dodgy code

#### 2. Apply the SpotBugs plugin using the Gradle documentation, run the check and take a look at the output. What do you see?