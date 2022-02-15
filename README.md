# ARMhf/ARM64 Linux only - meta-multimc
Auto Updating (cross-fingers) for MultiMC/Launcher Minecraft package metadata for ARM64 and ARMhf Linux. Use the `master-clean` branch for ARM64 and `master-clean-arm32` for ARMhf. Warning: No support will be given by Mojang or MultiMC for using this meta repo, all issues should be created via this repo.

The meta repo automatically updates with the help of the https://github.com/wei/pull project (this project accepts donations). Sometimes it can take a few hours for this meta repo to be updated, going to the https://pull.git.ci/process/theofficialgman/meta-multimc address might cause it to update sooner.

This repo includes LWJGL 2.9.4-nightly-20150209, backported versions of 3.1.6, 3.2.1, and 3.2.2 for armhf/arm64 compatibility, and a spoofed 3.1.2 (for prerelease 1.13 minecraft). It also includes jinput 2.0.7 (it appears that jinput 2.0.5 from mojang is actually closer to 2.0.7) built from source: https://github.com/jinput/jinput/tree/2.0.7 (a library used for game controllers on minecraft 1.12.2 and older, testing working with this mod: https://github.com/ljsimin/MinecraftJoypadSplitscreenMod).

The only library that does not have a native arm64/armhf version is the narrator library created by Mojang. This just means the in-game narrator is unavailable. If you know a way to get the source for this library and build it for armhf/arm64 linux, create an issue here.

All currently released versions of minecraft function on armhf (`master-clean-arm32` branch) and arm64 (`master-clean` branch) linux.

To use if building the current MultiMC/Launcher source, specify the below applicable cmake variable:<br>
arm64 linux:
```
-DLauncher_META_URL:STRING="https://raw.githubusercontent.com/theofficialgman/meta-multimc/master-clean/index.json" 
```
arm32 linux:
```
-DLauncher_META_URL:STRING="https://raw.githubusercontent.com/theofficialgman/meta-multimc/master-clean-arm32/index.json"
```

The lwjgl binaries are hosted here (both lwjgl2 and lwjgl3 with each version having its own branch):<br>
https://github.com/theofficialgman/lwjgl3-binaries-arm32<br>
https://github.com/theofficialgman/lwjgl3-binaries-arm64<br>

You can find the source code I used to create the binaries here:<br>
https://github.com/theofficialgman/lwjgl3 (check the `3.2.2-arm`, `3.2.1-arm`, and `3.1.6-arm` branches)<br>
https://github.com/theofficialgman/lwjgl (checkout the commit corresponding to `2.9.4-nightly-20150209`)

Big shoutouts to https://github.com/JJTech0130 who did some preliminary work in his repos to get arm64/armhf lwjgl 2/3 built for linux

In the event that this meta repo breaks or is not updating anymore, you can create an issue on this repo.
