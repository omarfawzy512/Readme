# DORA Metrics


How To Build:
=====

Primary build is supported with gradle. More info in the [wiki](https://github.com/rundeck/rundeck/wiki/Building-and-Testing).

Requirements: Java 1.8, NodeJs 16

Build with Gradle
---

Produces: `rundeckapp/build/libs/rundeck-X.Y.war`

    ./gradlew build

Docker Build
---

Uses the war artifact and produces a docker image.

Creates image `rundeck/rundeck:SNAPSHOT`, you can define `-PdockerTags` to add additional tags

    ./gradlew :docker:officialBuild

Documentation
======

Available online at <https://docs.rundeck.com/docs>

FAQ: <https://github.com/rundeck/rundeck/wiki/FAQ>

Development
======

Refer to the [IDE Development Environment](https://github.com/rundeck/rundeck/wiki/IDE-Development-Environment) to get set up using IntelliJ IDEA or Eclipse/STS.

* [Issue tracker](https://github.com/rundeck/rundeck/issues) at github.com

Do you have changes to contribute? Please see the [Development](https://github.com/rundeck/rundeck/wiki/Development) wiki page.

License
======

Copyright 2023 Rundeck, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
