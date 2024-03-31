---
{"dg-publish":true,"permalink":"/battleye-does-not-start-automatically-on-mac-or-linux/","tags":["gardenEntry"]}
---



ref: https://github.com/SmartlyDressedGames/Unturned-3.x-Community/issues/4403

TL;DR Mac/Linux does not load Battleye until joining a server. 

> `Unturned_BE.exe` adds `-BattlEye` to the launch command-line to indicate it was launched through BattlEye. This is used to decide whether to load modules and whether to show the "BattlEye disabled" banner on the menu. It looks like that banner is removed from the Mac and Linux versions because they don't receive that `-BattlEye` flag, i.e., they don't think they are running with BattlEye until joining the server. This means it _should_ be loading modules regardless. Can you attach the Client.log file, please? Your modules should be getting loaded.

wowkwowow