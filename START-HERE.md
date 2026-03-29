# Start Here

> [!TIP]
> If you're new, start with this file and `COPY-THIS-PROMPT.md` only.

A beginner should not design the whole system by hand on day one. The cleanest path is to let the primary agent recommend the smallest starter bundle first, then approve before any files are applied.

## Quick path
1. Open `COPY-THIS-PROMPT.md`.
2. Paste the prompt into the primary agent.
3. Let the primary agent choose the smallest suitable starter bundle.
4. Review the recommendation.
5. Approve before any files are applied.

## Keep in mind
| Do | Avoid |
| --- | --- |
| Start with the smallest viable bundle | Manually picking lots of roles immediately |
| Prefer explicit verification | Adding complexity because it sounds advanced |
| Review before applying files | Mixing multiple starter bundles at once |
| Keep the first system simple | Editing every shared contract before the first recommendation |

## Internal helper files
The primary agent may also read:
- `INTERNAL-BUNDLE-PICKER.md`
- files in `starter-bundles/`

Those files help the primary agent choose a bundle, but they are **not** the beginner front door.
