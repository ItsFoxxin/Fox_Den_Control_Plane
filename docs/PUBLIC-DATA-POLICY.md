# Public Data Policy

This repository is public. Commit only general-purpose governance, role specifications, synthetic fixtures, generic handoff templates, documentation and tests.

**Never commit:** secrets or access tokens; real internal IP addresses, service identifiers, topology or hostnames; private vulnerability disclosures; unredacted CI or application logs; actual user data; private Worker transcripts; deployment credentials; real rollback backups; completed sensitive repository profiles.

Safe repository identity and Issue/PR numbers may be documented when those resources are already public, but do not embed dated internal status inventories in governance templates.

If sensitive material is found, stop publishing and use the repository owner's approved incident-handling process. Deleting a later commit does not make secrets undisclosed.

No automatic CI publish, release or deployment action is authorized by this repository. Reference workflows should fail closed when evidence or approval is missing.
