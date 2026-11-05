# rig-template

Minimal template for a standalone rig application.

This repository is the starting point for new rig apps. It provides the shared
submodule wiring, build tooling, and containerized PipeWire development
environment used by `rig-looper`, `rig-meter`, and future apps.

## Submodules

- `core/` -> `https://github.com/isfopo/rig-core.git`
- `components/` -> `https://github.com/isfopo/rig-components.git`

Clone with submodules:

    git clone --recurse-submodules https://github.com/isfopo/rig-template.git

## Create a new app

1. Copy this template to a new repository.
2. Update the module path in `go.mod`.
3. Update import paths in `cmd/` and `internal/`.
4. Rename `BINARY` in the `Makefile`.
5. Replace the placeholder UI in `internal/ui` with the app's Bubble Tea model.
6. Update this README.

## Layout

    cmd/rig/        application entrypoint
    internal/ui/    app-specific terminal UI
    core/           rig-core submodule (audio, MIDI, tempo, config)
    components/     rig-components submodule (TUI primitives)
    scripts/        container entrypoint and PipeWire configuration
    Dockerfile
    docker-compose.yml
    Makefile

## Build (host)

Requires Go >= 1.24 and a C compiler for CGO (RtMidi):

    make build       # build ./rig
    make test        # run tests (root + submodules)
    make vet         # go vet
    make clean       # remove build artifacts

## Containerized development (Linux)

    docker compose build
    docker compose run --rm dev
    docker compose run --rm rig -engine test -demo

See `scripts/container-entrypoint.sh` and `scripts/pipewire/` for the PipeWire
rig details.
