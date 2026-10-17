# Mineshaft Server

Source fork of PowerNukkitX pinned at the version Mineshaft currently bundles.
See UPSTREAM.md for the upstream origin and the fork point.

## Why we have the source

Mineshaft ships the compiled `powernukkitx.jar` as an asset. That's the
runtime artifact. The source here exists so:

1. We can rebuild the JAR from source if upstream disappears
2. We can apply Mineshaft-specific patches (e.g. Android-friendly defaults,
   bugfixes we need before upstream merges them)
3. LGPL compliance — the user has the source corresponding to the binary we
   ship

## Rebuilding the JAR

PowerNukkitX uses Gradle. The upstream `README.md` has current instructions.
Expected flow:

```bash
./gradlew clean shadowJar
# Output: build/libs/powernukkitx.jar
```

Requires: JDK 21+, internet (for Gradle dependencies).

The output is a fat JAR (~80 MB) — matches the artifact at
`~/git/MineShaft/app/src/main/assets/powernukkitx.jar`.

## Updating to a new upstream version

```bash
git fetch upstream-pnx --tags
git checkout <new tag>          # e.g. 3.0.6
# Rebuild per above, drop the new JAR into Mineshaft:
cp build/libs/powernukkitx.jar ~/git/MineShaft/app/src/main/assets/powernukkitx.jar
# Bump the JRE_VERSION-like sentinel if needed, test on balin.
```
