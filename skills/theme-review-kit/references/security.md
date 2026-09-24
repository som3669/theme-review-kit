# WordPress Theme Security Review

Use this reference when reviewing security-related theme code.

## General Rule

Never report a security issue from a code pattern alone.

Read the surrounding code and determine:

1. Where the data comes from.
2. Whether it is trusted.
3. How it is processed.
4. Where it is stored.
5. Where it is output.

## Escaping

Check dynamic output for appropriate escaping.

Common escaping functions include:

- esc_html()
- esc_attr()
- esc_url()
- esc_textarea()
- wp_kses()
- wp_kses_post()

Choose escaping according to output context.

Do not blindly recommend esc_html() for every value.

## Sanitization

Check user-controlled input before storage or processing.

Examples include:

- sanitize_text_field()
- sanitize_textarea_field()
- sanitize_email()
- sanitize_key()
- sanitize_hex_color()
- esc_url_raw()

The correct sanitization depends on the expected data.

## Nonces

Check actions that modify data or perform sensitive operations.

Common functions include:

- wp_nonce_field()
- wp_verify_nonce()
- check_admin_referer()

A nonce is not an authorization mechanism.

## Capabilities

Check privileged operations for appropriate capability checks.

Example:

current_user_can()

Do not assume a nonce replaces a capability check.

## Database

Inspect direct database operations carefully.

Check:

- SQL preparation
- User-controlled values
- $wpdb usage

Do not report an SQL injection vulnerability without tracing the
actual data flow.

## Severity

Classify security findings carefully.

If exploitation or impact cannot be established from the available
code, explain the concern and mark it for manual verification.