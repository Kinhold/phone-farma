# phone-farma

## Status: concept / roadmap

This repository reserves a package boundary for an Android compute-worker
payload under Kinhold. It does not currently contain an Android application,
worker runtime, deployment system, or production-ready package.

No scaffold is included yet because the worker contract, execution sandbox,
supported Android versions, and trust model have not been specified. Publishing
an empty Android project would imply implementation progress that has not
happened.

## Intended package boundary

If developed, this repository would contain the device-side payload responsible
for accepting a narrowly defined compute job, enforcing resource limits,
reporting a result, and recovering safely from interruption. Fleet control,
job scheduling, payment, and general-purpose remote administration are outside
this package.

## Decisions required before implementation

1. Document the exact job schema and authenticated transport.
2. Define consent, enrollment, revocation, and operator visibility.
3. Select Android API levels and background-execution mechanism.
4. Define CPU, memory, thermal, battery, network, and storage limits.
5. Threat-model untrusted jobs, coordinators, devices, and result tampering.
6. Specify signing, reproducible builds, updates, rollback, and audit logs.
7. Add an emulator-based test plan before any physical-device deployment.

The project should remain a concept until those decisions are reviewed. In
particular, it must not become a hidden background worker or arbitrary remote
code execution channel.
