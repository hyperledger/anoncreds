# Hyperledger AnonCreds

![AnonCreds Logo](https://raw.githubusercontent.com/hyperledger/anoncreds-spec/main/spec/images/logo/hl_anoncreds_colour.svg)

Hyperledger AnonCreds is an opinionated implementation of verifiable credentials
using Zero Knowledge Proofs (ZKPs) to maximize privacy and unlinkability in the
sharing of verifiable data. Anoncreds v1 is based on CL Signatures, while v2 is
flexible enough to support different underlying signature schemes.

The open source AnonCreds v1 implementations
([here](https://github.com/hyperledger/indy-sdk/blob/master/libindy/src/api/anoncreds.rs)
in [Hyperledger Indy](https://www.hyperledger.org/projects/hyperledger-indy) and
[here](https://github.com/hyperledger/anoncreds-rs)) in [Hyperledger
AnonCreds](https://wiki.hyperledger.org/display/anoncreds) provide capabilities
that many see as important for digital identity use cases in particular, and
verifiable data in general. These features include:

- A full implementation of the Layer 3 verifiable credential “Trust Triangle” of the [Trust over IP Model](https://trustoverip.org/wp-content/toip-model/).
- Complete flows for issuing verifiable credentials (Issuer to Holder), and requesting, generating and verifying presentations of verifiable claims (Holder to Verifier).
- Fully defined data models for all of the objects in the flows, including verifiable credentials, presentation requests and presentations sourced from multiple credentials.
- Fully defined applications of cryptographic primitives.
- The use of Zero Knowledge Proofs (ZKPs) in the verifiable presentation process to enhance the privacy protections available to the holder in presenting data to verifiers, including:
  - Blinding issuer signatures to prevent correlation based on those signatures.
  - Holder binding based on the use of unrevealed identifiers to prevent correlation based a holder identifier.
  - Selective disclosure in the generation of presentations to minimize data sharing to that required for the business need.
  - The use of predicate proofs to reduce the sharing of PII and potentially correlating data, especially dates (birth, credential issuance/expiry, etc.).
  - A revocation scheme that proves a presentation is based on credentials that have not been revoked by the issuers without revealing correlatable revocation identifiers.

The AnonCreds working group produced the AnonCreds v1.0 specification that
describes the existing implementation minus any dependency on the Hyperledger
Indy ledger ("ledger-agnostic"). AnonCreds v2.0 has been started that adds new
capabilities while retaining the core features of AnonCreds v1 (listed above).
v2 includes features such as replacing CL Signatures with BBS Signatures (and
other schemes), and includes a more scalable revocation scheme. Those participating
in this Working Group define the direction of future versions of Hyperledger
AnonCreds.
