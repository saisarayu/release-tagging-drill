# Versioning Convention

## Semantic Versioning

All production releases use Semantic Versioning in the format:

`MAJOR.MINOR.PATCH`

### MAJOR

Increment MAJOR when a breaking or incompatible change is introduced.

Example:

`v1.4.2 -> v2.0.0`

### MINOR

Increment MINOR when a new backward-compatible feature is added.

Example:

`v1.4.2 -> v1.5.0`

### PATCH

Increment PATCH when a backward-compatible bug fix is released.

Example:

`v1.4.2 -> v1.4.3`

When MAJOR or MINOR is increased, lower version numbers reset to zero.

---

## Tag Naming Format

All production release tags use:

`vMAJOR.MINOR.PATCH`

Example:

`v1.5.0`

The `v` prefix is required and must be used consistently for every release.

---

## Annotated Tags

Production releases use annotated Git tags instead of lightweight tags.

Annotated tags are preferred because they store release metadata such as the
tag message, author, and date.

Example:

```bash
git tag -a v1.5.0 -m "Release 1.5.0: add optional export feature"
git push origin v1.5.0