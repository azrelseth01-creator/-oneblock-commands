# OneBlock Commands (Fabric, Minecraft 26.2 / 26.3)

Adds `/ob ...` commands. The OneBlock datapack is bundled inside the mod jar,
so you only need the one jar (plus Fabric API). Do NOT also keep the separate
OneBlockGenerator datapack in your world, or the two copies can conflict.

## Build
Needs Java 25 and Gradle 9.6 (9.5.1 or newer also works for 26.2).

    gradle wrapper --gradle-version 9.6.0     # once, creates ./gradlew
    ./gradlew build                           # jar ends up in build/libs/

(Windows: `gradlew.bat build`.) Use the file named oneblock-commands-1.0.0.jar,
not the -sources one. Put it in the server's `mods/` folder with Fabric API.

To build against 26.3 instead of 26.2, edit the three version lines marked
in gradle.properties. The same jar is declared compatible with both versions.

## Commands (operators only, same as /function)
    /ob help
    /ob status
    /ob reload
    /ob block <block id>                 e.g. /ob block minecraft:diamond_block
    /ob setblock here                    moves it to your feet, always grass
    /ob setblock <x> <y> <z>             always grass, must be inside the zone
    /ob phase add|remove|set <phase>     add = forward, remove = back, set = jump
                                         phase: 1-12, plains forest desert jungle swamp
                                         taiga caves lush_caves deep_dark nether end void,
                                         next, prev (also accepts phase10)
    /ob zone set                         centre the zone on you
    /ob zone radius <blocks>
    /ob events <loot%> <mob%>            0 = off
    /ob cleanup

First time in a new world: stand near the OneBlock position and run `/ob reload`.

## No Java/Gradle on your PC? Let GitHub build the jar
1. Create a free GitHub repository and upload everything in this folder
   (including the hidden .github folder).
2. Open the repo's "Actions" tab, wait for the "build" run to finish (green check).
3. Open the run and download the "oneblock-commands" artifact. Unzip it and use
   oneblock-commands-1.0.0.jar (not the -sources one).
