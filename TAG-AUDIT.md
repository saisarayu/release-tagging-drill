# Tag Audit

## 1. `version-1.0` — Non-standard naming

The tag uses `version-1.0` instead of the team's proposed `vMAJOR.MINOR.PATCH`
format.

This makes the release history inconsistent and prevents predictable semantic
version sorting.

### Risk

A developer cannot reliably compare this release with standard SemVer tags.
Automated release tooling may also fail to interpret the version correctly,
making rollback and deployment tracking less reliable.

---

## 2. `release_2` — No semantic version information

The tag `release_2` does not communicate the MAJOR, MINOR, or PATCH level of
the release.

### Risk

The team cannot determine whether this release introduced a breaking change,
a new backward-compatible feature, or only a bug fix. This makes release
comparison and rollback decisions harder during an incident.

---

## 3. `1.5.0` — Missing `v` prefix

The tag `1.5.0` follows the numeric SemVer structure but does not follow the
repository's required `vMAJOR.MINOR.PATCH` naming convention.

### Risk

Mixing `1.5.0` with tags such as `v1.4.2` creates inconsistent naming and can
cause confusion in scripts, release tooling, and human interpretation of the
release history.

---

## 4. `v2-final-FINAL` — Ambiguous release name

The tag `v2-final-FINAL` does not identify a precise semantic version and uses
the ambiguous word `FINAL`.

### Risk

If multiple final versions are created, developers cannot determine which one
came first or what changed between them. During an outage this can turn
rollback into guesswork.

---

## 5. Inconsistent tag history — Multiple naming conventions

The repository mixes standard-looking SemVer tags with names such as
`version-1.0`, `release_2`, `1.5.0`, and `v2-final-FINAL`.

### Risk

The release history cannot be treated as one predictable, sortable sequence.
This makes it harder to identify the current production release, compare
releases, audit deployments, and select the correct rollback target.