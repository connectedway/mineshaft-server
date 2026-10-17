# Upstream provenance

This repository is a fork of `PowerNukkitX/PowerNukkitX`, a Java implementation
of the Minecraft Bedrock Dedicated Server protocol. We maintain this fork
independently so Mineshaft's bundled server is not exposed to upstream repo
disappearance, archiving, or breaking API changes.

## Fork point

- Upstream: https://github.com/PowerNukkitX/PowerNukkitX
- Tag at fork time: `3.0.5` (commit `9813b75a9` — "chore: bump API version to 3.0.5")
- Date forked: 2026-10-17
- Protocol compatibility: Minecraft Bedrock 1.26.50 (protocol 2193)

## Remote

Upstream retained as `upstream-pnx` for later cherry-picks and tag updates.
No `origin` is configured; set one when a remote hosting location is chosen.

```
git remote -v
# upstream-pnx  https://github.com/PowerNukkitX/PowerNukkitX.git
```

## License

PowerNukkitX is **LGPL-3.0**. See LICENSE in this directory. Mineshaft bundles
and distributes the compiled `powernukkitx.jar`; the LGPL allows this provided:

1. We publish any modifications we make (that's this fork — public)
2. We allow users to replace the library with their own version
3. We clearly attribute PowerNukkitX in Mineshaft's About screen with a link
   back to this fork's source

Because Mineshaft invokes PowerNukkitX via `ProcessBuilder` (a separate OS
process), LGPL section 4 is satisfied — Mineshaft itself does not become
LGPL-infected.

## Related

- `~/git/MineShaft` — the Android app that bundles this server
- `~/git/mineshaft-jdk` — the OpenJDK runtime the server runs on
