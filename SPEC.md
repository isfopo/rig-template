# rig-template — Specification

## Purpose

`rig-template` is the starting point for new standalone rig applications. It
provides submodule wiring, build tooling, and the containerized PipeWire
development environment.

## Included

- `core/` submodule: `rig-core`
- `components/` submodule: `rig-components`
- Makefile and Docker/PipeWire development setup
- Minimal Bubble Tea application in `cmd/rig` and `internal/ui`

## Creating an app

1. Copy the template.
2. Update the module path and imports.
3. Rename the binary in the Makefile.
4. Replace the placeholder UI.
5. Update README, SPEC, and NOTES for the new app.
