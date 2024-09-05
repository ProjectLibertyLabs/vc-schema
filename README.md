# vc-schema

This is a repository for Verifiable Credential JSON Schema files.

## Testing a schema

A useful tool for testing JSON Schema is `ajv`.

```
% npm i -g ajv ajv-formats
% ajv --spec=draft2020 -c ajv-formats validate -s schema.json -d credential.json
```

## Adding a schema

The convention for this repository is to name schema URLs according to their `title` and content hash.
A content hash is a useful way of ensuring that the exact intended version of a schema is referenced from a credential.

- Make a directory under `docs/` named according to the schema `title` property (if one does not yet exist)
- Determine a multihash for the file (sha2-256 or blake3) and encode as a base32 string
- Add the file to the new directory with the filename created by appending ".json" to the base32 multihash

There are various tools to calculate the multihash for a file, one approach is as follows:

```
% cat schema-file.json | ipfs add -nq --cid-version=1 | ipfs cid format -f %m
bciqjspnbwpc3wjx4fewcek5daysdjpbf5xjimz5wnu5uj7e3vu2uwnq
```

The output is the base32-encoded sha2-256 multihash to use in the filename.

You can additionally use the [Multiformat Inspector](https://libertydsnp.github.io/multiformat-inspector/) to check the digest against the output from `sha256sum`.
