# Semgrep Hot Spot Rules - Work in Progress
Repository for my Semgrep hot spot rules.

## What's a Hot Spot?
In this context, hot spots are parts of code that *might* contain security
vulnerabilities. You are not "always" looking for a specific problem, but rather
bad practices, common mistakes, insecure configurations, and in short, places
where bad things usually happen.

For more details and examples, please read the blog post at
https://parsiya.net/blog/semgrep-hotspot/.

## The Audience
The audience for these rules are security engineers who want to find focus areas
for code review. These rules are noisy and are not suitable for developer facing
views and systems.

## Quick Start

1. Clone the repository.
2. Run Semgrep with `--config` pointing to the repository or any of the
   subdirectories.

`$ semgrep --config /path/to/semgrep-hotspots/ . --sarif --output my-results.sarif`

## Rules
A list of rules and their triage guides. If you have any questions or have
suggestions please make an issue.

TODO: Add rules and their guides here.

Rule ID | Language | Triage Guide
--- | --- | ---
[Arrays passed to functions](cpp/arrays-passed-to-functions.yaml) | C++ | [Triage Guide](cpp/arrays-passed-to-functions.md)
[Encode/Decode in function name](cpp/encode-decode-function-name.yaml) | C++ | [Triage Guide](cpp/encode-decode-function-name.md)
[Encrypt/Decrypt in function name](cpp/encrypt-decrypt-function-name.yaml) | C++ | [Triage Guide](cpp/encrypt-decrypt-function-name.md)
[memcpy usage](cpp/memcpy-insecure-use.yaml) | C++ | [Triage Guide](cpp/memcpy-insecure-use.md)
[snprintf usage](cpp/snprintf-insecure-use.yaml) | C++ | [Triage Guide](cpp/snprintf-insecure-use.md)

## Contribution
Please follow the [Contributing through GitHub][con-gh] section of
`Contributing to Semgrep rules` article and make a pull request with your rules.
Please note the [LICENSE](LICENSE).

At a minimum, add a rule with a good Semgrep message, tests (which can double as
example code) and a short triage guide. The triage guide should explain why the
rule is a hot spot and how a fellow security engineer can triage the results.

If in doubt, please use the current rules as reference or make an issue (or
contact me via another way). Make sure to update the guide table in the readme.

TODO: Add info about the directory structure. 

TODO: Add info about severity level.`WARNING` seems like a good choice. Ask the r2c team for their opinion.

[con-gh]: https://semgrep.dev/docs/contributing/contributing-to-semgrep-rules-repository/#contributing-through-github

## LICENSE
Attribution-NonCommercial-ShareAlike 4.0 International. Please see
[LICENSE](LICENSE) for details. I chose this license based on the
[Trail of Bits public Semgrep rules repository][tob-rules].

[tob-rules]: https://github.com/trailofbits/semgrep-rules