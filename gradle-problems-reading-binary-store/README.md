Reproduces <https://github.com/gradle/gradle/issues/14220>.

Instructions:

1. Run `./gradlew dependencies -s`.
   Build fails with
   ```
   Problems reading data from Binary store in $HOME/.gradle/.tmp/gradle15654238986865481472.bin offset 19565 exists? true
   Problems loading the resolution results (0.006 secs). Read 308 values, last was: 5
   Corrupt serialized resolution result. Cannot find selected component (1874) for runtime -> com.netflix.archaius:archaius-core:0.3.3
   ``` 
2. Switch order of dependencies in [build.gradle](build.gradle).
3. Run `./gradlew dependencies -s`.
   Build succeeds.
