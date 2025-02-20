# v0.1.1
### Fixes
* Fix sha256 generation : long keys are now decoded correctly. Reported in https://github.com/klaxit/hidden-secrets-gradle-plugin/issues/16
* Random string generation was not including lower case characters
### Improvements
* The plugin search for `Secrets.kt` to add other keys instead of using package's name to access it.
* Resolve package from the Kotlin file to edit the C++ file to be able to use a different package than the package of Secret.kt to encode/decode keys.
* Clearer error message for `hideSecret` command
* Clearer logs
* Tasks name become public
* Use more constants in code to avoid regression
* Automatic tests added
* Detekt added to the project to ensure Kotlin coding style
### Migration from 0.1.0
* To take advantage of the sha256 generation fix you need to :
1) Remove files : `secrets.cpp`, `sha256.cpp` and `Secrets.kt` from your project (that will delete all your keys previously added)
2) You need to re-add all your keys with `hideSecret` command (will copy new cpp files and encode your key)
# v0.1.0
* First release
