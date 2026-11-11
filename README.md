# Dimasik JAR build

This repository contains the GitHub Actions workflow for compiling the Dimasik Fabric client.

## Required source files

The source archive is split into three pieces. Upload **all three files together** to the repository root (the same level as this README), then press **Commit changes**:

- `dimasik.zip.part-00`
- `dimasik.zip.part-01`
- `dimasik.zip.part-02`

Attaching the files to a ChatGPT conversation does not place them in this GitHub repository. After committing, confirm that all three names appear on the repository's **Code** page.

The workflow joins the parts and checks the SHA-256 before extracting. It also accepts the complete archive as `dimasik-source.zip` or `dimasik.zip` if it is added through another upload method.

## Build environment

- Java 25
- Gradle 9.9.1
- Fabric Loom version declared by the project

The workflow verifies the Gradle project structure, performs only narrowly scoped safety replacements when the original strings are present, builds the mod, and uploads the resulting JAR as the `Dimasik-JAR` artifact.

## Download

Open **Actions**, select the latest **Build Dimasik JAR** run, and download `Dimasik-JAR` after the run succeeds.

If the run fails at **Locate, verify, and extract source**, check that all three source-part files are committed to the repository root. If it fails later, open the failed step for the actual Gradle or Java error.
