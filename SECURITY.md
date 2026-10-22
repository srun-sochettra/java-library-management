# Security guidance

This is a local console exercise, not a hardened library service. No supported-release programme, security audit or response deadline is established here.

## Input and data boundaries

Regex checks constrain numeric format but do not prevent integer overflow. Large inputs and repeated additions can consume resources; do not expose the program as an untrusted-input service without separate limits and validation.

Catalogue data exists only in memory. There is no authentication, durable storage, loan audit trail or recovery mechanism. Do not use the program as the sole record of real library activity.

The application loads a third-party formatter JAR. Its binary contents were not inspected during this refresh. Review its provenance and applicable terms before distributing or replacing it.

## Reporting

For ordinary defects, provide the JDK, dependency setup, input sequence and expected versus observed behaviour using synthetic data.

For sensitive concerns, use a verified private maintainer channel if available, or request one without publishing sensitive details. No dedicated security mailbox or enabled private-reporting feature is confirmed by the supplied files.

This document describes boundaries; it does not implement fixes or certify safety.
