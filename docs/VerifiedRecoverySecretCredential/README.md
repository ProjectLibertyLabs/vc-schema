# Verified Recovery Secret Credential

Used to communicate the Frequency Recovery Secret in a standard way.

## Fields

### `recoverySecret`

The human-readable form of the Recovery Secret.
It should be all uppercase in the range: 0-9, A-F (hexadecimal).
Total of 64 characters with chunks of 4 characters separated by `-`.

Example: `69EC-2382-E1E6-76F3-341F-3414-9DD5-CFA5-6932-E418-9385-0358-31DF-AFEA-9828-D3B7`

## Resources

- [Frequency Design Document for the Recovery System](https://github.com/frequency-chain/frequency/blob/main/designdocs/recovery_system.md)
- [Recovery JavaScript SDK](https://github.com/frequency-chain/frequency/tree/main/js/recovery-sdk#readme)
