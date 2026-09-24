# ThemeReviewKit

ThemeReviewKit is an open-source Claude Code skill designed to assist
human reviewers when reviewing themes submitted to the WordPress.org
Theme Directory.

It helps analyze both Classic and Block themes and organizes findings
into clear review categories.

## Features

- Classic Theme review
- Block Theme review
- Theme Review requirement checks
- Security review
- Escaping and sanitization checks
- Internationalization checks
- Licensing checks
- Privacy and remote-resource checks
- Plugin-territory checks
- Manual testing checklist
- Trac-ready review formatting

## How It Works

ThemeReviewKit first determines the type of theme being reviewed.

```
Theme
  |
  +-- Classic Theme
  |     `-- Classic Theme checks
  |
  `-- Block Theme
        `-- Block Theme checks
```

It then performs the common Theme Review checks and classifies
findings as:

- REQUIRED
- RECOMMENDED
- NEEDS MANUAL VERIFICATION

## Installation

Copy the `theme-review-kit` skill directory into your Claude Code
skills directory.

For a project-level installation:

```
.claude/
`-- skills/
    `-- theme-review-kit/
        |-- SKILL.md
        `-- references/
```

## Usage

Open the theme you want to review with Claude Code.

Ask Claude:

```
Review this theme using ThemeReviewKit.
```

Claude should first determine whether the theme is a Classic or
Block theme and then apply the appropriate review process.

## Important

ThemeReviewKit is a review assistant.

AI-generated findings can contain mistakes or false positives.
Always verify findings before posting them to a WordPress.org
Theme Trac ticket.

The human reviewer remains responsible for the final review.

## Official Requirements

ThemeReviewKit is designed around the official Theme Review
requirements:

https://make.wordpress.org/themes/handbook/review/required/

Because these requirements can change, always check the current
official documentation when reviewing a theme.

## Disclaimer

ThemeReviewKit is an independent open-source project and is not
affiliated with or endorsed by the WordPress Foundation or the
WordPress open-source project.

WordPress is a registered trademark of the WordPress Foundation.

## License

```
ThemeReviewKit
Copyright (C) 2026 ThemeReviewKit contributors

This project is licensed under the GNU General Public License,
version 2 or, at your option, any later version.
```

See the LICENSE file.
