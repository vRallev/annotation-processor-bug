# Annotation processor bug

Shows that there seems to be a bug in the Android Gradle plugin `2.4.0-alpha3`. Running `./gradlew build` will print

```
:app:compileDebugJavaWithJavac - is not incremental (e.g. outputs have changed, no previous execution, etc.).
error: Bad service configuration file, or exception thrown while constructing Processor object: javax.annotation.processing.Processor: Provider com.evernote.android.state.StateProcessor could not be instantiated: java.lang.NoClassDefFoundError: com/evernote/android/state/State
:app:compileDebugJavaWithJavac FAILED
```

But this class is definitely included. Maybe there's an issue with the classpath. Using the Android Gradle plugin `2.3.0` works fine.
