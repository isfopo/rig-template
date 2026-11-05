# rig-template — Notes

## Build and run

Requires Go >= 1.24 and a C compiler for CGO where applicable:

    make build
    make test
    make vet

## Container development

    docker compose build
    docker compose run --rm dev
    docker compose run --rm rig

The PipeWire bootstrap and virtual sink configuration are in `scripts/`.
