# ThemeReviewKit

A Claude Code plugin with one skill that helps human reviewers review
themes submitted to the WordPress.org Theme Directory. There is no code
to build or test: the product is Markdown instructions.

## Layout

- `skills/theme-review-kit/SKILL.md`: the entry point. It defines the
  review workflow, the finding classes and the report format.
- `skills/theme-review-kit/references/*.md`: loaded only when they
  apply. `classic-themes.md` and `block-themes.md` must stay separate,
  so that a Block theme review never pulls in Classic-only rules and
  the other way round.
- `.claude-plugin/plugin.json`: the plugin manifest. Its `name` is
  `theme-review-kit`, and that is also the install name.
- `.claude-plugin/marketplace.json`: makes this repo a marketplace of
  its own (`source: "./"`).

## Editing the skill

- The only authority is the official requirements at
  https://make.wordpress.org/themes/handbook/review/required/. Never add
  a requirement that is not there, and never promote a best practice to
  REQUIRED.
- Keep the three finding classes exactly as they are: REQUIRED,
  RECOMMENDED, NEEDS MANUAL VERIFICATION.
- The skill never declares a theme passed or failed. The human reviewer
  decides.
- The Trac response stays a separate step, used only for findings the
  reviewer has verified.
- If you change the report format or the prompts, update the Usage
  section of `README.md` to match.

## Distribution

- The plugin is listed in Anthropic's community marketplace. It passed
  review on 2026-09-24. Install with
  `theme-review-kit@claude-plugins-community`.
- The catalog pins a commit, and CI moves the pin forward on new
  pushes. Installed users only receive an update when `version` in
  `plugin.json` changes.
- Before every release, run `claude plugin validate .` and
  `claude plugin validate .claude-plugin/plugin.json --strict`.
- The version number is the maintainer's decision. Do not bump it or
  tag it unless asked.

## History & open items

- 2026-09-24: submitted via https://platform.claude.com/plugins/submit
  to `anthropics/claude-plugins-community` (the curated
  `claude-plugins-official` takes no applications). Form: name
  "ThemeReviewKit", platform Claude Code only, GPL-2.0-or-later, no
  privacy URL. Passed review the same day; the catalog syncs nightly, so
  the entry may lag approval.
- Open: version stays 0.1.0 or goes to 1.0.0, and whether to push a git
  tag. The maintainer decides.
- Open: Cowork support is untested. Test it before adding that
  platform.
- Open: README/LICENSE credit "ThemeReviewKit contributors" while
  `plugin.json` says "Som Shrestha".

## Naming and licensing

- Do not put "WordPress" in the plugin's name. It is a trademark of the
  WordPress Foundation. Keep the "not affiliated" disclaimer in the
  README.
- The license is GPL-2.0-or-later, in both `LICENSE` and `plugin.json`.

## Conventions

- JSON and Markdown files end with a newline.
- Commit messages are plain sentences in the imperative mood, for
  example "Document installing from the Claude Code community
  marketplace".
