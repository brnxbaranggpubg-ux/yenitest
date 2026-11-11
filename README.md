# Dimasik build

This repository contains the GitHub Actions build setup for the Dimasik project.

## Upload source

The original source archive is larger than GitHub's normal browser upload limit for a single file, so it is split into three pieces. Upload all three files to the repository root in one commit:

- `dimasik.zip.part-00`
- `dimasik.zip.part-01`
- `dimasik.zip.part-02`

After the upload, the **Build Dimasik JAR** workflow starts automatically. It joins the pieces, extracts the archive, installs Java 25 and Gradle 9.9.1, and runs the Gradle build.

## Download the result

Open the repository's **Actions** tab, select the latest **Build Dimasik JAR** run, and download the `Dimasik-JAR` artifact if the workflow succeeds.

The source archive has not been committed yet; only the build workflow and this README are present until the three archive parts are uploaded.
