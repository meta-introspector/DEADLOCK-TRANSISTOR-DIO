# Onboarding Guide — DEADLOCK-TRANSISTOR-DIO

Welcome to the kagenti ecosystem! This guide gets you from clone to running service.

## Quick Start

```bash
cd /home/mdupont/git/github.com/deadsg235/DEADLOCK-TRANSISTOR-DIO
make install
make dev
```

## Prerequisites

### Option A: Nix (recommended)
```bash
nix develop   # drops you into a shell with all deps
make dev
```

### Option B: Manual
```bash
# see Makefile
make run
```

## Project Structure

- `Makefile` — build/dev/test/clean targets
- `flake.nix` — reproducible Nix dev environment
- Service port: **9116**

## Testing

```bash
make test
```

## kagenti Integration

This repo is registered as a kagenti agent in the `deadsg` namespace.

| Field | Value |
|-------|-------|
| Agent name | `deadsg-deadlock-transistor-dio` |
| Namespace | `deadsg` |
| Type | `unknown` |
| Port | `9116` |
| Health | `http://127.0.0.1:9116/` |

### systemd

```bash
# Install the service
cp systemd/deadsg-deadlock-transistor-dio.service ~/.config/systemd/user/
systemctl --user daemon-reload
systemctl --user enable --now deadsg-deadlock-transistor-dio

# Check status
systemctl --user status deadsg-deadlock-transistor-dio
curl http://127.0.0.1:9116/
```

## Monster Group Orbifold

Your repo maps to orbifold coordinate **(28, 25, 39)** in the 196,883-cell Monster torus (71 × 59 × 47).

- Conformal weight: h = 1.6479
- Bott class: B4
- Eigenspace: Earth

This coordinate is used by the FRACTRAN navigator and CFT analysis tools.

## erdfa Shards

Source files are content-hashed to DA51 CBOR shards for the erdfa content-addressed layer.

```bash
make erdfa   # regenerate shard index
```

## Contributing

1. Fork this repo
2. `nix develop` for reproducible environment
3. Make changes, `make test`
4. PR back to `deadsg235/DEADLOCK-TRANSISTOR-DIO`

## Links

- [kagenti ecosystem](https://github.com/meta-introspector/kagenti)
- [notebooklm-tools](https://github.com/meta-introspector/notebooklm-tools)
- [FRACTRAN breeder](https://github.com/meta-introspector/fractran-breed-rs)
