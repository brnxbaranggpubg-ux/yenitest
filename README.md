# Dimasik build

This repository contains the GitHub Actions build setup for the Dimasik project.

## Source upload

Upload all three original archive parts to the repository root in one commit:

- `dimasik.zip.part-00`
- `dimasik.zip.part-01`
- `dimasik.zip.part-02`

The workflow verifies the assembled archive SHA-256 before extracting it. A mismatch stops the build.

## Build

The workflow uses Java 25 and Gradle 9.7.1 for the Minecraft 26.2 target. It also adjusts Fabric dependency scopes and nests the LuaJ and ONNX Runtime libraries into the mod JAR.

For safety, the build patch disables the built-in connection to the third-party IRC host, removes hard-coded Minecraft server-address redirects, and changes the Windows media helper from hidden PowerShell with ExecutionPolicy Bypass to a visible process using RemoteSigned. These changes can disable features that depended on those external services or redirects.

## Download

After the source parts are committed, open **Actions** and select the latest **Build Dimasik JAR** run. Download the `Dimasik-JAR` artifact only when the workflow succeeds.

The original source archive is not yet in this repository, so no build run or JAR artifact exists yet.
