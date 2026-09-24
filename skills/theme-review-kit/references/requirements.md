# WordPress.org Theme Review Requirements

## Purpose

Use this document when reviewing themes submitted to the
WordPress.org Theme Directory.

The official WordPress Theme Review Requirements are the authority.

Official requirements:
https://make.wordpress.org/themes/handbook/review/required/

Do not invent requirements.

If a possible issue cannot be confirmed from the official requirements,
classify it as "Needs Manual Verification" instead of "Required".

## Requirement Categories

Check the theme against these areas:

1. Licensing & copyright
2. Privacy
3. Accessibility
4. Code
5. Functionality and Features
6. Plugins
7. Naming, spelling, and trademarks
8. Language & internationalization
9. Files
10. Classic themes
11. Block themes
12. Theme settings pages and onboarding
13. Selling, credits, links, and spam
14. Theme author and theme upload restrictions

## Classification

### REQUIRED

Use only when the issue violates an applicable WordPress.org
Theme Review requirement.

A required finding must include:

- File
- Line number when available
- Relevant code
- Explanation
- Applicable requirement
- Suggested correction
- Official reference

### RECOMMENDED

Use for improvements that are good practice but are not grounds
for preventing theme approval.

Never present a recommendation as a requirement.

### NEEDS MANUAL VERIFICATION

Use when:

- Context is missing
- The rule is unclear
- Runtime behavior must be tested
- Licensing cannot be confirmed
- Visual behavior must be tested
- The issue requires reviewer judgment

Do not convert uncertainty into a required issue.

## Important Review Rules

Read the relevant file and surrounding code before reporting an issue.

Do not report an issue based only on pattern matching.

Determine whether the theme is a Classic Theme or Block Theme before
applying theme-type-specific requirements.

Do not apply Classic Theme requirements to Block Themes unless the
requirement also applies to Block Themes.

Do not apply Block Theme requirements to Classic Themes.

When checking a WordPress function, hook, filter, class, or API,
consult the official WordPress Developer Resources when necessary.

Do not reject a theme because of personal coding or design preferences.

Design suggestions must not be presented as required issues unless
the design causes an actual applicable requirement or usability issue.

## Licensing

Check:

- Theme license
- Theme copyright
- Third-party libraries
- Fonts
- Images
- Bundled assets
- External resources

Everything distributed in the theme must have an acceptable license.

Resources should have appropriate source, copyright, and licensing
information.

Potential licensing uncertainty should be marked for manual
verification.

## Privacy and Remote Resources

Check for:

- Remote requests
- External APIs
- Tracking
- Analytics
- Remote images
- Remote JavaScript
- Remote CSS
- CDN resources

Do not assume a remote request is allowed.

Determine whether explicit user consent is required.

## Plugins and Plugin Territory

Check whether the theme:

- Bundles plugins
- Automatically installs plugins
- Downloads plugins automatically
- Requires plugins unnecessarily
- Implements functionality considered plugin territory

Recommended plugins must comply with current Theme Directory
requirements.

Potential plugin-territory questions that are not clear should be
marked "Needs Manual Verification".

## Files

Check:

- style.css
- readme.txt
- required theme files
- licensing information
- bundled resources
- development files
- source files for minified assets

Check style.css headers against current requirements.

Do not rely on an old remembered list of required headers.

## Internationalization

Check visible user-facing text for internationalization.

Check:

- Translation functions
- Text domains
- Escaping combined with translation
- Theme text domain
- User-facing strings

Do not flag strings that do not require translation.

## Final Rule

A theme should only be considered ready for approval when all confirmed
required issues have been resolved.

Claude assists the human reviewer.

Claude does not make the final WordPress.org approval decision.