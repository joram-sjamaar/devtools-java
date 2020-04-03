# Java Project: Week 3

In dit project werken we aan de **Java** opdracht. Hierin werken we aan:
 * ~~Gradle en Java~~
 * ~~Code Analyse~~
 * Multi-module projecten
 
## Inhoudsopgave
- [Java Project: Week 3](#java-project--week-3)
  * [Inhoudsopgave](#inhoudsopgave)
  * [Splitting up the project.](#splitting-up-the-project)
  * [Making sure it works!](#making-sure-it-works-)
  * [Submit your Java project](#submit-your-java-project)
 
## Splitting up the project.
 
#### 5. Run gradle tasks and notice the difference(s) between the project from last week and this week

**What obvious differences do you see? (You might need to use the --all option!)**

Het grote verschil dat ik zie is dat alle tasks nu per 'module' zijn. Alles heeft de prefix `core` of `app`.
Ook zie je dat `core` bijvoorbeeld wel de optie 'Sonarqube' heeft, maar app niet.

**What about the tasks for Spotbugs, Jacoco and Sonarqube? What happened to them?**

Die kun je nu indivueel runnen per module. De output van deze wordt geplaatst in de betreffende module. Bijv: `.\core\build\reports\spotbugs`

## Making sure it works!

```
> Task :otherapp:run
If you can read this, the import was succesful!
```

## Submit your Java project

Ik weet dat checkStyle meerdere keren runt. Dit is express, omdat ik wil voldoen aan de eis 'maak een extra stap voor checkstyle en Spotbugs'.