# Question Routing

This contract defines where uncertainty should be routed.

## Routing principles
- Route questions to the party most able to resolve them with the least delay.
- Prefer bundled clarification over serial one-question loops.
- Do not ask the operator for information that can be gathered safely through research or local context.
- A worker should route uncertainty to the primary agent first unless the missing information clearly belongs with the human requester.
- Do not guess when missing information changes scope, risk, approval posture, or acceptance criteria.

## Routing table
| Question type | Default destination |
| --- | --- |
| missing objective, success criteria, audience, or delivery target | human requester or approver |
| missing execution order, dependencies, or work breakdown | planner |
| missing facts, sources, or outside context | researcher |
| missing defect analysis or quality gap review | critic |
| missing verification, acceptance criteria, or evidence checks | verifier |
| messy intake, duplicate requests, or unstructured briefs | intake coordinator |
| domain-specific marketing strategy or messaging choices | marketing strategist |
| worker uncertainty during active orchestration | primary agent first |
| unclear permissions, policy uncertainty, or risky next steps | escalation |

## Ask the human only when
- the objective or success criteria remain unclear
- approval is required
- only the human can provide the missing credential, file, or business rule
- multiple materially different paths exist and choosing one changes the outcome significantly

## Recommended question shape
- what is missing
- why it matters
- default assumption if no answer is provided
- smallest decision needed to continue
