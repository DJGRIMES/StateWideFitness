# Agent Instructions (Statewide Fitness)

## Source of truth
- **Globals** live in `base/globals.json` for shared data (contact info, identity).
- **Voice and naming** live in `base/voice.json` (tone, terminology).
- **Section schemas** live in `base/section-types.json`.
- **Section order and nav** live in `base/manifest.json`.
- **Section content** lives in `content/index/*.json`.
- **Design standards** live in `base/design-spec.json`.

## Data usage rules
- Contact values must come from `base/globals.json` and be referenced in content using string tokens:
  - `{{globals.contact.phone.display}}`
  - `{{globals.contact.email.display}}`
  - `{{globals.contact.address.full}}`
- Keep city spelling consistent with `base/voice.json` (use **Mt. Pleasant**).
- Use the `base/voice.json` gym name terminology (currently **Statewide Fitness**).
- Contact must remain obfuscated in rendered HTML using encoded `data-*` attributes and be decoded at runtime via the page script (do not ship plaintext contact values directly in markup).

## Section conventions
- `type` values must match `base/section-types.json` exactly (lowercase keys like `embed`).
- Content files should only contain values that are specific to that section.

## Editing checklist
- Keep JSON valid (no trailing commas, no truncated files).
- Ensure any new references to globals use the token format above.
- Update `base/manifest.json` when adding or removing sections.
