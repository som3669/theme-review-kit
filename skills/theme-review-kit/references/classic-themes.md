# Classic Theme Review

Use this reference only when reviewing a Classic WordPress theme.

The current official Theme Review Requirements are the authority:
https://make.wordpress.org/themes/handbook/review/required/

Do not apply Classic Theme requirements to a Block Theme unless
the requirement independently applies to both theme types.

# 1. Detect a Classic Theme

A Classic Theme primarily uses PHP templates.

Typical files include:

- index.php
- header.php
- footer.php
- sidebar.php
- functions.php
- single.php
- page.php
- archive.php
- comments.php
- search.php
- 404.php

Do not determine the theme type from one file alone.
Inspect the overall theme structure.

# 2. Required Theme Structure

Check the theme's required files against the current official
WordPress Theme Review Requirements.

For Classic Themes, pay particular attention to:

- style.css
- index.php
- comments.php when required by the applicable requirements
- screenshot requirements
- readme.txt requirements for WordPress.org submission

Do not report a missing optional template as a required issue.

# 3. Document Structure

Check for a valid DOCTYPE declaration.

Check that the theme uses:

    language_attributes()

Example:

    <html <?php language_attributes(); ?>>

# 4. Required WordPress Hooks and Functions

Check for the appropriate use of:

    wp_head()
    wp_footer()
    wp_body_open()
    body_class()
    post_class()
    wp_link_pages()

Check that wp_head() appears immediately before the closing head
where appropriate.

Check that wp_footer() appears immediately before the closing body
where appropriate.

Check wp_body_open() immediately after the opening body element.

Always inspect the surrounding template before reporting an issue.

# 5. Required Theme Support

Check for:

    add_theme_support( 'title-tag' );
    add_theme_support( 'automatic-feed-links' );

Do not confuse recommended theme support with required theme support.

# 6. Standard Template Functions

When the corresponding standard template files are used, check that
they are loaded using their WordPress template functions.

Examples:

header.php:

    get_header();

footer.php:

    get_footer();

sidebar.php:

    get_sidebar();

searchform.php:

    get_search_form();

Do not automatically report an issue simply because one of these
files does not exist.

# 7. Custom Template Files

Check custom template loading.

Where applicable, use WordPress template APIs such as:

    get_template_part()
    locate_template()

Inspect the actual implementation before deciding that a requirement
has been violated.

# 8. Front Page

Check that the theme respects the WordPress front-page settings.

The theme should correctly handle:

- latest posts
- static front page

Do not require a specific visual design.

Review functionality, not personal design preference.

# 9. Permissions

For theme options, check the appropriate capability.

The Theme Review Requirements specify:

    edit_theme_options

Do not use a user's role such as:

    administrator

as a substitute for a capability check.

Also investigate inappropriate capabilities such as:

    manage_options
    edit_themes

when they are being used for ordinary theme-option access.

# 10. Scripts and Styles

Check that scripts and styles use the appropriate WordPress APIs.

Typically inspect:

    wp_enqueue_script()
    wp_enqueue_style()
    wp_enqueue_scripts

Check for:

- hard-coded scripts
- hard-coded styles
- bundled WordPress libraries
- inappropriate remote resources
- dependencies
- versioning

Apply the general Theme Review Requirements.

# 11. Security

Use security.md.

Pay particular attention to:

- escaping
- sanitization
- nonces
- capabilities
- database queries
- URLs
- user-controlled input

Never report a vulnerability without understanding the data flow.

# 12. Internationalization

Check visible user-facing text.

Inspect:

    __()
    _e()
    esc_html__()
    esc_html_e()
    esc_attr__()
    esc_attr_e()

Check appropriate text-domain usage.

Do not require translation functions for values that should not
be translated.

# 13. Comments

Check comment functionality when applicable.

Do not confuse recommended comment features with mandatory
Theme Review requirements.

# 14. Manual Testing

Identify things that require runtime testing, including:

- menus
- comments
- front-page setting
- pagination
- widgets
- Customizer options
- responsive layout
- keyboard navigation
- skip links
- JavaScript interactions

If code inspection cannot confirm the issue, mark:

NEEDS MANUAL VERIFICATION

# Final Rule

Classify every finding as:

- REQUIRED
- RECOMMENDED
- NEEDS MANUAL VERIFICATION

Never turn a recommendation into a requirement.

Never fail a theme because of personal coding or design preference.