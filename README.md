#Gauge plugin installation
Gauge provides only few IDE plugins. The complete list can be found here: https://gauge.org/plugins/

This description describes how to setup VSCode and IntelliJ plugins.

##Install Gauge
Fist of all install `Gauge` itself.

Install gauge with brew:
```shell script
brew update
brew install gauge
```
There is an open issue regarding gauge telemetry function, that can stop the gauge plugin. To avoid this turn the feature off.  Here is the description of the problem: https://github.com/getgauge/Intellij-Plugin/issues/392

Turn off gauge telemetry:
```shell script
gauge telemetry off
```
Install gauge plugins
```shell script
gauge install js
gauge install java
gauge install python
```

Install gauge python package:
```shell script
pip install getgauge
```

##Setup IntelliJ - java
1. Install gauge plugin: `Preferences... -> Plugins -> Gauge`
2. Create a new Gauge project: `File -> New -> Project...`
3. Select Gauge as project type on the left, then click `Next`
4. Select the folder that you would use with Gauge plugin, then click `Finish`. Now there are generated files that needed for a Gauge project and added sample files, too. There are 3 files that's needed for sure: `java.properties`, `manifest.json`, `<project_name>.iml`, other can be deleted.
5. Add `STEP_IMPL_DIR = java/src/test/java` line to the end of `java.properies`
6. Modify `sourceFolder` field under `content` element in `<project_name>.iml`. E.g: 
 `
<sourceFolder url="file://$MODULE_DIR$/java/src/test/java" isTestSource="false" />
`
7. Reload the project

##Setup VSCode - js, python
Install Gauge extension
###NodeJS
1. Create inside the `env/default` folder a `js.properties`file
2. Change the value `Language` field of `manifest.json` to `js`
3. Reload the window

###Python
1. Create inside the `env/default` folder a `python.properties`file
2. Change the value `Language` field of `manifest.json` to `python`
3. Reload the window

####Important
In `env/default` folder always one language specific properties file can remain.

The `"Language"` field of `manifest.json` file should match the properties file in `env/default` folder

Here you can fine language specific properties files:
https://github.com/vmatyusGitHub/gauge-properties
