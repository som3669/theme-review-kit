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

ThemeReviewKit is a Claude Code skill. There is nothing to build and no
dependencies to install — it is Markdown, and installing means copying
one directory.

You need [Claude Code](https://claude.com/claude-code).

### Install as a plugin

The shortest route. In Claude Code, add this repository as a plugin
marketplace, then install from it:

```
/plugin marketplace add som3669/theme-review-kit
/plugin install theme-review-kit
```

Update later with:

```
/plugin marketplace update theme-review-kit
```

If you would rather copy the skill in by hand, use one of the two
installations below instead. Start by cloning:

```bash
git clone https://github.com/som3669/theme-review-kit.git
```

### Project-level installation

Installs the skill for one project only.

```bash
cp -r theme-review-kit/skills/theme-review-kit /path/to/your-project/.claude/skills/
```

On Windows:

```powershell
Copy-Item -Recurse theme-review-kit\skills\theme-review-kit "C:\path\to\your-project\.claude\skills\"
```

The result:

```
your-project/
`-- .claude/
    `-- skills/
        `-- theme-review-kit/
            |-- SKILL.md
            `-- references/
```

### User-level installation

Installs the skill once, for every project.

```bash
cp -r theme-review-kit/skills/theme-review-kit ~/.claude/skills/
```

On Windows:

```powershell
Copy-Item -Recurse theme-review-kit\skills\theme-review-kit "$env:USERPROFILE\.claude\skills\"
```

### Check the installation

Start Claude Code and run:

```
/theme-review-kit
```

Skills are loaded when a session starts. If Claude Code was already
running, restart it.

### Repository layout

```
theme-review-kit/
│
├── README.md
├── LICENSE
│
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
│
└── skills/
    └── theme-review-kit/
        ├── SKILL.md
        └── references/
            ├── requirements.md
            ├── security.md
            ├── classic-themes.md
            ├── block-themes.md
            ├── review-checklist.md
            └── trac-response.md
```

The reference files are loaded only when they apply, so a Block theme
review does not pull in Classic theme rules.

## Usage

### Review a theme

Extract the submitted ZIP, then start Claude Code in the theme
directory:

```bash
unzip theme-name.zip -d theme-name
cd theme-name
claude
```

Ask Claude:

```
Review this theme using ThemeReviewKit.
```

Claude should first determine whether the theme is a Classic or
Block theme and then apply the appropriate review process.

### Narrower requests

You do not have to run a full review every time:

```
Review this theme for security issues only.
Is this a Classic or Block theme?
Check the licensing and any bundled libraries.
What still needs manual testing?
```

### Prepare the Trac comment

Once you have checked the findings yourself:

```
Turn the verified findings into a Trac comment.
```

This is a separate step on purpose. Verify before you post.

### What you get back

A report in a fixed structure:

- Theme information — name, version, theme type, review type
- Required issues — file, line, evidence, applicable requirement,
  suggested correction
- Recommended — optional improvements, listed separately
- Needs manual verification — what to test, and why static inspection
  cannot confirm it
- Review summary — counts for each category

ThemeReviewKit will not tell you the theme passes or fails. That
decision stays with you.

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
