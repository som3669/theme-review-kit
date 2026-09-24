# Block Theme Review

Use this reference only when reviewing a WordPress Block Theme.

The current official Theme Review Requirements are the authority:
https://make.wordpress.org/themes/handbook/review/required/

Do not apply Classic Theme-only requirements to a Block Theme.

# 1. Detect a Block Theme

A Block Theme primarily uses block templates.

Look for:

    theme.json
    templates/
    parts/
    patterns/

A key structure is:

    templates/index.html

Do not classify a theme from the presence of theme.json alone.
Inspect the complete theme structure.

# 2. Required Files

For a WordPress.org Block Theme review, check for:

    style.css
    readme.txt
    theme.json
    templates/index.html

index.html must be inside:

    templates/

Example:

theme-name/
├── style.css
├── readme.txt
├── theme.json
└── templates/
    └── index.html

Missing required files should be reported as REQUIRED when confirmed.

# 3. style.css

Check the required theme headers.

Use the general requirements.md reference for the current required
style.css headers.

Do not rely on remembered or outdated header requirements.

# 4. readme.txt

Check that the required readme.txt exists and complies with the
current WordPress.org requirements.

Also inspect:

- licensing
- copyright
- bundled resources
- resource attribution
- privacy documentation when applicable

# 5. theme.json

Inspect theme.json.

Check:

- valid JSON
- schema/version where applicable
- settings
- styles
- template configuration
- custom settings
- referenced assets

Do not report personal style preferences as requirements.

# 6. Templates

Inspect:

    templates/

At minimum, verify:

    templates/index.html

Block templates must be complete.

Check for:

- malformed block markup
- missing closing block comments
- incorrect closing block comments
- invalid block structure

Example block markup:

    <!-- wp:group -->
    ...
    <!-- /wp:group -->

Do not report formatting preferences as errors.

# 7. Template Parts

Inspect:

    parts/

when present.

Check block markup and references.

Examples may include:

    parts/header.html
    parts/footer.html

Do not require optional template parts simply because other themes
commonly include them.

# 8. Patterns

Inspect:

    patterns/

when present.

Check:

- PHP errors
- escaping where applicable
- internationalization
- licensing of images/assets
- remote resources
- invalid block markup
- inappropriate functionality

Do not require patterns merely because they are recommended.

# 9. PHP

Block Themes may still contain PHP.

For example:

    functions.php
    patterns/*.php

PHP must still meet the general requirements.

Check:

- PHP errors
- security
- escaping
- sanitization
- prefixing
- internationalization
- WordPress APIs

Being a Block Theme does not exempt PHP from the general requirements.

# 10. Scripts and Styles

If the Block Theme loads additional CSS or JavaScript, check:

- WordPress enqueue APIs
- dependencies
- bundled libraries
- remote resources
- minified/source files
- licensing

Use the general Theme Review Requirements.

# 11. Security

Use:

    security.md

Check all applicable PHP and JavaScript.

Do not assume that a Block Theme cannot contain security problems.

# 12. Internationalization

Check translatable user-facing strings.

This can include strings in:

- PHP
- patterns
- theme configuration
- administrative interfaces

Apply the current internationalization requirements.

# 13. Licensing

Inspect:

- images
- fonts
- patterns
- JavaScript
- CSS
- third-party libraries
- demo assets

Use requirements.md.

Do not assume an image is allowed simply because it is used inside
a block pattern.

# 14. Remote Resources

Check for remote:

- images
- fonts
- scripts
- styles
- APIs
- data

Apply the current privacy and remote-resource requirements.

# 15. Manual Testing

Test or flag for manual testing:

- Site Editor
- templates
- template parts
- navigation
- styles
- style variations
- patterns
- front page
- single posts
- pages
- archives
- search
- 404
- responsive layout
- keyboard navigation

When static code review is insufficient, classify the finding as:

NEEDS MANUAL VERIFICATION

# Final Rule

Classify findings as:

- REQUIRED
- RECOMMENDED
- NEEDS MANUAL VERIFICATION

Do not apply Classic Theme-only requirements such as PHP template
structure to a Block Theme unless an applicable general requirement
also requires it.

Do not reject a theme because of personal design preferences.