# WordPress.org Theme Review Checklist

## Phase 1 — Identify Theme Type

Determine:

- Classic Theme
- Block Theme
- Child Theme
- Hybrid/other relevant structure

Do this before applying theme-specific requirements.

## Phase 2 — Basic Files

Inspect:

- style.css
- readme.txt
- functions.php when present
- theme.json when present
- templates
- template parts
- inc/includes directories
- JavaScript
- CSS
- bundled libraries

## Phase 3 — Licensing

Check:

- Theme copyright
- Theme license
- Third-party resources
- Fonts
- Images
- JavaScript libraries
- CSS libraries
- Bundled assets
- Resource attribution

## Phase 4 — Security

Check:

- Escaping
- Sanitization
- Nonces
- Capability checks
- User input
- Database operations
- URLs
- File operations

## Phase 5 — WordPress APIs

Check:

- Hooks
- Filters
- Enqueue functions
- Theme support
- Template functions
- WordPress bundled libraries
- Deprecated functionality

## Phase 6 — Functionality

Look for functionality that may belong in a plugin.

Do not automatically report uncertain plugin-territory cases.

Mark uncertain cases for manual verification.

## Phase 7 — Internationalization

Check:

- User-facing strings
- Translation functions
- Text domain usage
- Escaped translations

## Phase 8 — Privacy

Look for:

- Remote requests
- Tracking
- Analytics
- External resources
- APIs
- Data collection

## Phase 9 — Theme-Type Checks

If Classic Theme:

Read classic-themes.md.

If Block Theme:

Read block-themes.md.

## Phase 10 — Runtime / Manual Testing

Identify issues that cannot be confirmed statically.

Examples:

- Layout
- Customizer behavior
- Editor behavior
- Responsive behavior
- JavaScript interactions
- Accessibility behavior

Mark these as requiring manual testing.

## Phase 11 — Final Review

Group findings into:

1. Required
2. Recommended
3. Needs Manual Verification

Never mix recommendations with requirements.

For every Required issue include evidence.