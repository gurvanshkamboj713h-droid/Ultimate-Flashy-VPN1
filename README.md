# Ultimate Flashy VPN — Fabric 1.21.11 prototype

This is a complete Gradle/Fabric source project using official Mojang mappings and Java 21.

## Included in this prototype
- Cozy dark-purple proxy settings screen opened from the Minecraft pause menu.
- SOCKS5 and HTTP CONNECT proxy selection.
- Optional username/password fields.
- Save/load one local profile.
- A proxy tunnel test to `example.com:443` with elapsed time.
- GitHub Actions workflow that builds the JAR and uploads it as an artifact.

## Important limitations
This is **not yet a working VPN for Minecraft gameplay**. The test button verifies that the configured proxy can establish a tunnel to `example.com:443`; it does not route Minecraft's server connection through that proxy, does not change the game's exit IP, and does not promise lower ping. Minecraft traffic routing and fail-closed behavior are not implemented in this milestone.

The profile is saved in `config/ultimate-flashy-vpn.properties`. The password is stored as plain text in that file. Do not save a sensitive password here until secure credential storage is added.

## Build with GitHub Actions
1. Upload the contents of this folder into the root of your GitHub repository, keeping the folder structure.
2. Open **Actions** and run **Build Ultimate Flashy VPN**, or push a commit to `main`.
3. Open the successful workflow run and download the `Ultimate-Flashy-VPN` artifact.
4. Extract the artifact and copy the `.jar` into the Minecraft `mods` folder alongside Fabric API.

Target: Minecraft 1.21.11, Fabric Loader 0.18.4, Java 21.
