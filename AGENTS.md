# Repository workflow

When the user says `push this` in chat, treat it as authorization to finish the
Git workflow for the current repository:

1. Review the working tree and diff for the user's current changes.
2. Check for accidentally included credentials, secrets, or unrelated generated files.
3. Run checks appropriate to the changes, when available.
4. Stage the intended changes and commit with a concise, descriptive message.
5. Push the current branch to its configured remote, setting the upstream if needed.
6. Report the commit and push result briefly.

Do not ask for routine confirmation before committing or pushing after this phrase.
Do not force-push, discard user changes, or rewrite existing commits without explicit
authorization. If there are no new changes, push any existing unpushed commits.
If authentication, permissions, or a remote conflict prevents the push, explain
the specific blocker without claiming success.

## Run code shortcut

When the user says `runcode` in chat, run the active file identified by the latest
IDE context. If the user names a file explicitly, run that file instead. If no
file can be identified, ask which file to run.

Read the file and relevant project instructions first, then use the appropriate
runtime and working directory. For Python files, prefer the project's virtual
environment when available; otherwise use `python3`. Do not ask for routine
confirmation to run ordinary local code. Existing permission requirements still
apply to destructive actions or external side effects.

Report the program output or the specific execution error briefly. Do not commit
or push as part of this shortcut.
