# did:bio - DID Method Specification

**[Read the specification -> did-bio-spec.md](did-bio-spec.md)**

`did:bio` is a [W3C DID 1.0](https://www.w3.org/TR/did-1.0/) conformant
decentralized identifier method for biological research data - datasets,
researchers, and research infrastructure - using the **Solana blockchain**
as its verifiable data registry.

| | |
|---|---|
| Method name | `bio` |
| Example | `did:bio:devnet:2T6zLFvMx7NJac5qQtiKTaPhMwHLkwKETWjUK1yKv4tc` |
| Verifiable data registry | Solana (`bio-did-registry` program) |
| Program ID | `H1gnV4GjNT3UV7AgGNUCkSaciuVVtM7hKb8JhPV3Xxy6` (live on devnet) |
| Reference implementation | <https://github.com/ekayana-labs/bio-did-registry> |
| Status | Draft - pending registration in [W3C DID Extensions](https://www.w3.org/TR/did-extensions-methods/) |

## Highlights

- **Generative resolution** - every Ed25519 keypair is a resolvable DID at
  zero cost; on-chain state is optional and unlocks key rotation, services,
  and controllers.
- **Sponsored creation** - account initialization is permissionless and
  grants the payer no control, so platforms can pay fees while researchers
  keep sole authority.
- **Permanent deactivation** - a rent-refunding on-chain tombstone; the
  registry can never revert a deactivated DID to its generative state
  (unlike close-account designs).
- **Current W3C key formats** - `Multikey` / `publicKeyMultibase` per
  [Controlled Identifiers v1.0](https://www.w3.org/TR/cid-1.0/), plus an
  experimental post-quantum ML-DSA-87 verification method type.

## Related repositories

- [`bio-did-registry`](https://github.com/ekayana-labs/bio-did-registry) - the
  Solana registry program (Pinocchio, `no_std`, zero allocation) and its
  LiteSVM test suite
- [`did-bio-core`](https://github.com/ekayana-labs/did-bio-core) - transport free
  Rust resolver library implementing this specification
- [`bio-did-registry`](https://github.com/ekayana-labs/bio-did-registry) - the
  `bio-did-resolver` CLI for resolving and updating DIDs on live cluster
## License

[MIT](LICENSE)
