# Reproducer

https://github.com/JavierSegoviaCordoba/semver-gradle-plugin/issues/175

Run

```
./gradlew printSemver
```

Should be something like:

```
> Task :printSemver
semver for semver-repro-175: 1.0.0
```

Now use:

```
semver { mapVersion { "1.0.0" } }
```

and try again:

```
FAILURE: Build failed with an exception.

* What went wrong:
Could not determine the dependencies of task ':build'.
> Could not create task ':printSemver'.
   > Could not isolate value com.javiersc.semver.project.gradle.plugin.valuesources.VersionValueSource$Params_Decorated@e87f257 of type VersionValueSource.Params
      > Could not serialize value of type $Proxy92

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
> Get more help at https://help.gradle.org.

BUILD FAILED in 648ms
```
