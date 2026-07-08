# User Onboarding

Use this note when a new user installs the skill and wants personalization.

Recommended default:

- do not scan historical conversations automatically
- do not infer a long-term user profile silently
- ask a short first-run onboarding instead

Minimum onboarding topics:

1. output language
2. human-first vs AI-first readability
3. summary density
4. evidence-boundary placement
5. main domain tendency

Recommended outcome:

- create a user-specific preferences file based on `users/template/preferences.template.md`
- use a short first-run onboarding prompt instead of freeform profile guessing

Recommended execution order:

1. ask the first-run onboarding questions
2. summarize the user's answers back in compact form
3. write or propose a user-specific `preferences.md`
4. ask for confirmation before changing an existing preferences file

Primary execution prompt:

- see [onboarding-prompt.md](./onboarding-prompt.md)
- for a saved target example, see [examples/onboarding-output.preferences.example.md](./examples/onboarding-output.preferences.example.md)

Optional later refinement:

- after repeated use, propose updates to the user profile
- require explicit confirmation before writing changes

Guardrail:

- onboarding is for presentation defaults and task tendency only
- onboarding should not rewrite artifact model, router logic, evidence protocol, or coverage protocol
