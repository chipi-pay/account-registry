# Contributing an Account Implementation

## Submission Checklist

### Required
- [ ] Class hash declared on StarkNet mainnet
- [ ] SRC-6 standard account interface (`__validate__`, `__execute__`)
- [ ] Repository with source code (any license)
- [ ] JSON entry following `schema.json`

### Recommended (for paymaster compatibility)
- [ ] SRC-5 interface registration
- [ ] SNIP-9 outside execution (`outside_execution_v2`)
- [ ] Open-source license (MIT, Apache-2.0)

### Optional (earns "Audited" badge)
- [ ] Audit report link
- [ ] 0 critical/high findings

## How to Submit

1. Fork this repository
2. Create `accounts/your-account-name.json` following the schema
3. Open a PR with your submission
4. CI validates your JSON and verifies the class hash exists on mainnet
5. Chipi team reviews for compatibility
6. On merge, `registry.json` is auto-updated

## Account Entry Format

See `schema.json` for the full schema. Example:

```json
{
  "id": "my-custom-account",
  "name": "My Custom Account",
  "type": "CUSTOM",
  "version": "1",
  "classHash": "0x...",
  "network": "starknet_mainnet",
  "license": "MIT",
  "author": {
    "name": "Your Name",
    "github": "your-github"
  },
  "repository": "https://github.com/you/your-repo",
  "capabilities": ["sessions", "multicall"],
  "standards": {
    "src5": true,
    "src6": true
  },
  "audit": {
    "audited": false
  },
  "deprecated": false
}
```

## Audit Levels

Audit is a badge, not a gate:

1. **Not in registry** — Users pass `classHash` directly in SDK. Works fine.
2. **In registry, unaudited** — `audit.audited: false`. SDK recognizes it. No badge.
3. **In registry, audited** — `audit.audited: true` + report link. Gets "Audited" badge.

Personal/experimental accounts welcome. Just submit with `audit.audited: false`.
