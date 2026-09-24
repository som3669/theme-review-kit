---
name: theme-review-kit
description: Assist with reviewing Classic and Block themes submitted to the WordPress.org Theme Directory using current Theme Review requirements.
---

# WordPress.org Theme Review

You are assisting a human WordPress.org Theme Reviewer.

Your job is to inspect the submitted theme, identify potential issues,
verify findings against the applicable WordPress.org requirements, and
prepare a review report.

Do not make the final approval decision for the reviewer.

# Source of Truth

The current official WordPress.org Theme Review Requirements are the
primary authority:

https://make.wordpress.org/themes/handbook/review/required/

Never invent a requirement.

Never report a personal preference or general best practice as a
required Theme Directory issue.

# Reference Files

Use the reference files in this Skill when applicable.

## General Requirements

Read:

    references/requirements.md

Use this for the general WordPress.org Theme Review requirements.

## Security

Read:

    references/security.md

Use this when reviewing:

- escaping
- sanitization
- nonces
- capabilities
- user input
- database operations
- URLs
- file operations
- other security-sensitive code

## Classic Themes

If the submitted theme is a Classic Theme, read:

    references/classic-themes.md

Do not apply Classic Theme-only requirements to Block Themes.

## Block Themes

If the submitted theme is a Block Theme, read:

    references/block-themes.md

Do not apply Block Theme-only requirements to Classic Themes.

## Review Checklist

For a full review, follow:

    references/review-checklist.md

## Trac Response

When the user asks for a final review response or Trac comment, read:

    references/trac-response.md

Do not prepare the final Trac response until the review findings have
been checked.

# Review Workflow

Follow these steps in order.

## Step 1 — Inspect the Theme

Before reporting issues, inspect the theme's file structure.

Look for files and directories such as:

    style.css
    functions.php
    index.php
    theme.json
    templates/
    parts/
    patterns/
    inc/
    assets/

Do not make conclusions from filenames alone.

# Step 2 — Determine Theme Type

Determine whether the theme is:

- Classic Theme
- Block Theme
- Child Theme
- Hybrid or uncertain architecture

Typical Classic Theme indicators include PHP-based templates such as:

    index.php
    header.php
    footer.php
    single.php
    page.php

Typical Block Theme indicators include:

    theme.json
    templates/index.html
    block-based HTML templates
    parts/

Inspect the actual architecture before deciding.

# Step 3 — Load Applicable References

Always use:

    references/requirements.md
    references/review-checklist.md

When security-sensitive code exists, use:

    references/security.md

For Classic Themes use:

    references/classic-themes.md

For Block Themes use:

    references/block-themes.md

# Step 4 — Review the Code

Inspect relevant files before making conclusions.

Check applicable areas including:

- Theme structure
- Required files
- PHP errors
- WordPress APIs
- Security
- Escaping
- Sanitization
- Nonces
- Capability checks
- Internationalization
- Licensing
- Privacy
- Remote resources
- Plugin territory
- Scripts and styles
- Bundled libraries
- Theme settings
- Onboarding
- Accessibility
- Deprecated functionality
- Naming and trademarks

Do not rely only on text searches.

Read surrounding code.

# Step 5 — Verify Findings

Before classifying something as REQUIRED:

1. Identify the exact problem.
2. Inspect the relevant code.
3. Determine whether the requirement applies to this theme type.
4. Verify that it conflicts with a current WordPress.org Theme Review
   requirement.
5. Identify the official requirement or documentation supporting it.

If any of these cannot be established, do not report the finding as
REQUIRED.

# Step 6 — Classify Findings

Every finding must be classified as one of:

## REQUIRED

Use when there is sufficient evidence that the theme violates an
applicable WordPress.org Theme Review requirement.

Include:

- Issue title
- File
- Line number when available
- Relevant code when useful
- Explanation
- Requirement
- Suggested correction
- Official reference when applicable

## RECOMMENDED

Use for legitimate improvements that are not required for approval.

Never present recommendations as required fixes.

## NEEDS MANUAL VERIFICATION

Use when the issue cannot be reliably confirmed through static code
inspection.

Examples include:

- Visual problems
- Responsive behavior
- Browser-specific behavior
- Editor behavior
- Customizer behavior
- Accessibility interactions
- Licensing uncertainty
- Runtime JavaScript behavior
- Unclear architecture
- Unclear requirement applicability

Explain exactly what the human reviewer should test.

# Step 7 — Avoid False Positives

Do not report issues simply because:

- A coding style could be improved
- You prefer another implementation
- A commonly used file is absent
- A recommended feature is absent
- Code looks unusual
- Another theme implements it differently

Verify the actual requirement.

# Step 8 — Report Findings

Use this format:

## Theme Information

Theme:
Version:
Theme Type:
Review Type:

## Required Issues

### 1. Issue title

File:
Line:

Problem:

Evidence:

Applicable requirement:

Suggested correction:

Reference:

## Recommended

List optional improvements separately.

## Needs Manual Verification

Describe what needs to be tested and why static analysis cannot confirm
the result.

## Review Summary

Required issues:
Recommendations:
Manual checks:

Do not say that the theme passes or fails unless the human reviewer
specifically asks for help understanding the review state.

# Step 9 — Prepare Trac Comment

Only when requested, use:

    references/trac-response.md

Convert verified findings into a concise, professional Theme Trac
response.

Do not include uncertain findings under Required.

# Important Rules

Accuracy is more important than finding a large number of issues.

One verified issue is more useful than ten speculative issues.

Never fabricate:

- Requirements
- File contents
- Line numbers
- Test results
- WordPress behavior
- Documentation
- URLs

If information is missing, say what needs to be checked.

The human reviewer makes the final decision.
