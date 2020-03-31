# Some ramblings

## Anywise vs Pairwise DIDs

ESSIF-MVP1 uses “classic” ledger-based DIDs (i.e. DIDs registered on a Blockchain). Other types of DIDs are currently under development, such as “peer” DIDs that are not registered on a blockchain/DLT.

ESSIF-MVP1 uses “classic” ledger-based DIDs (i.e. DIDs registered on a Blockchain). Other types of DIDs are currently under development, such as “peer” DIDs that are not registered on a blockchain/DLT.

The following considerations apply to “classic” ledger-based DIDs:

* They can be called “omnidirectional” or “anywise” identifiers, because anyone (with “reading” access to the DLT used for DID registration) can resolve them “globally”.

* They require privacy considerations due to certain attributes of Blockchains (e.g. immutability) which are in tension with the GDPR.

* They are particularly useful for DID Subjects who are Issuers of Verifiable Credentials (because Verifiable Credentials contain information about the Issuer, e.g. their DID).

* They are resolved using a global “source of truth” based on strong consistency and integrity guarantees offered by Blockchains and similar networks.

The following considerations apply to “peer” DIDs:

*They can be called “unidirectional” or “pairwise” identifiers, meaning that only one party other than the DID Subject (or a limited group of parties) can resolve them.

* The use of such identifiers is considered best practice under a principle known as “directed identity” and since they are not registered on a Blockchain there are no tensions with data protection regulations.

* They may have weaker consistency and integrity guarantees than “classic” ledger-based DIDs (because they are not stored on a Blockchain).

## Well Known DID Configuration (DIF)

[](https://identity.foundation/specs/did-configuration/)

Assume that an entity has the following domain: `example.com`
Then at the URL `https://www.example.com/.well-known/did-configuration` there should be a document like the following, with a JSON object containing a DID string and cryptographic proof (in the form of a JWT signed with the specified DID's keys) that verifies **the domain controller and the DID controller are the same entity**.

```json
{
  "entries": [
    {
      "did": "did:ala:quor:redt:123...",
      "jwt": "ewogICJAY29udGV4dCI..."
              ↑ EXAMPLE OF DECODED JWT VALUE
              {
                "iss": "did:ala:quor:redt:123...",
                "domain": "example.com",
                "exp": 1475878357
              }
    }
  ]
}
```
## Consent receipt specification

file:///C:/Users/hesus/Downloads/consent-receipt-specification-v1-1-0.pdf