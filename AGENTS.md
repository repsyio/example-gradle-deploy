# AGENTS.md

Sample that publishes a Java library to a Repsy Maven repository with Gradle (`maven-publish`).

Sibling samples: `example-gradle-deploy`, `example-gradle-usage`, `example-maven-deploy`, `example-maven-usage`
(the `*-usage` samples consume what the matching `*-deploy` sample publishes, group `io.repsy.example`, version 1.0).
They back articles on https://docs.repsy.io; they are not Repsy product code, so the Repsy Jira and PR rules do not apply.

## Layout
- `build.gradle`: `java` and `maven-publish` plugins, group `io.repsy.example`, version `1.0`; publishes to `repsyUrl` with `repsyUsername` and `repsyPassword` Gradle properties.
- `src/main/java/io/repsy/example/gradle_deploy/Hello.java`: the library class. `gradlew`: wrapper (Gradle 9.8.2).

## Commands
- Build: `./gradlew build` (Gradle 9.8.2 wrapper; needs a JDK it supports).
- Publish: `./gradlew publish` needs `repsyUrl`, `repsyUsername`, `repsyPassword` (credentials; do not run unasked). No tests or CI.

## Conventions
- Default branch `master`. Few commits; titles are short free-form sentences, no ticket prefix; squash merges add ` (#N)`.
- `.github/dependabot.yml` exists (Dependabot only, no CI).
- Keep the sample minimal and in line with the docs article linked in `README.md`.
- Never put real credentials or a real username in the files; the Repsy URL and credentials are placeholders or properties.
