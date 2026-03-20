# Chipi Account Registry

Public registry of StarkNet account implementations compatible with [Chipi Pay](https://chipipay.com).

## What is this?

This registry documents account contract class hashes that work with Chipi's gasless infrastructure. Projects can submit their account implementations via PR, and the SDK can optionally fetch from this registry to recognize wallet types.

## Structure

```
accounts/           # Individual account JSON entries
registry.json       # Auto-generated from accounts/*.json
schema.json         # JSON schema for account entries
CONTRIBUTING.md     # Submission guide
```

## For SDK Users

The SDK works without this registry. Default wallet types (CHIPI, READY) are built in. This registry is for:

- **Custom accounts**: Pass `classHash` directly in `createWallet()`
- **Discovery**: Browse available account implementations
- **Audit badges**: See which accounts have been audited

## For Account Developers

See [CONTRIBUTING.md](./CONTRIBUTING.md) to submit your account implementation.

## Official Accounts

| Name | Type | Version | Class Hash | Audited |
|------|------|---------|------------|---------|
| Chipi Session Account | CHIPI | v33 | `0x0484bbd...` | Yes (Nethermind) |
| Chipi Session Account | CHIPI | v32 | `0x35a2251...` | Yes (Nethermind) |
| Argent X v0.4.0 | READY | - | `0x036078...` | Yes (Argent) |
