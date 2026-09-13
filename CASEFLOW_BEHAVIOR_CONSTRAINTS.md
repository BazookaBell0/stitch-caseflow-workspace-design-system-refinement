# Caseflow Worker behavior constraints

These rules exist so design regeneration does not invent behavior that the current product does not support.

## Current Worker MVP is online-only

Quick Capture is memory-only before explicit Save.

A capture is considered successfully saved only after the authenticated Caseflow API confirms server persistence.

On save failure:
- keep the in-memory draft when possible;
- clearly communicate that Save did not succeed;
- allow retry.

Do **not** generate current-product behavior or screens for:
- Waiting to sync
- saved offline
- local queue/outbox
- offline recovery
- service-worker/PWA persistence
- IndexedDB capture storage
- offline access leases

Those concepts are not part of the current Worker MVP.

## Real capabilities that design output should preserve

- Microsoft/Entra sign-in
- organization/program selection and switching
- assigned caseload
- deliberate same-program coverage lookup
- client workspace
- Current / rolling brief with explicit revision-checked Save
- Quick Capture with explicit server-backed Save
- recent Quick Captures
- client Tasks create/edit/complete/reopen
- exact privacy preview / protected formatting flow

## Future-designed areas

The repository also contains approved visual states for later product phases such as Today, global Tasks, Documentation / To Document, and protected follow-up workflows.

Preserve their approved visual language when designing the complete product, but do not infer backend semantics beyond what the real application later provides.

## Privacy fidelity

The privacy-review mock content is illustrative.

Production implementation must display actual protected output from Caseflow's privacy pipeline. Do not fabricate placeholder counts, names, mappings, or private-detail detection results merely to match example copy.

## Coverage

Coverage is deliberate same-program access and must remain visually distinct from an assigned caseload client. Opening a coverage client does not reassign that client.

## General rule

If a design artifact implies behavior that conflicts with these current constraints, preserve the surrounding approved visual design and correct only the conflicting behavior. Do not redesign unrelated screens around the constraint.
