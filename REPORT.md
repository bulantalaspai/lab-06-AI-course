# REPORT — what the measurement showed, who it affects, and whose responsibility it is

## 1. Measurement read-out

The Colab Tesla T4 run screened 200 matched pairs, 40 per row below, with Qwen2.5-3B-Instruct. The bare run produced 0 unparseable replies out of 400, fewer than I predicted. Each pair varies only the field under study. The flip rates use 95% Wilson intervals. The signed and absolute score means use 95% paired bootstrap intervals.

| Pair group | Bare flips, rate [95% CI] | Bare score differences | Bare mean absolute score gap [95% CI] | Bare signed mean, B minus A [95% CI] |
|---|---:|---:|---:|---:|
| Name language | 2/40, 5.0% [1.4%, 16.5%] | 11/40 | 3.12 [1.38, 5.25] | +1.62 [−0.38, +4.00] |
| Gender coding of name | 4/40, 10.0% [4.0%, 23.1%] | 6/40 | 1.12 [0.25, 2.13] | −0.62 [−1.75, +0.25] |
| University tier | 1/40, 2.5% [0.4%, 12.9%] | 10/40 | 2.50 [1.12, 4.12] | +1.75 [+0.25, +3.38] |
| Same-group name floor | 0/40, 0.0% [0.0%, 8.8%] | 7/40 | 2.00 [0.62, 3.62] | +0.25 [−1.25, +2.00] |
| Same-tier university floor | 1/40, 2.5% [0.4%, 12.9%] | 9/40 | 2.12 [0.88, 3.62] | −0.38 [−2.00, +1.12] |

Both name flip estimates exceeded the same-group name floor, with overlapping intervals. The university flip estimate equalled its floor. On absolute score movement, the language and university estimates were above their respective floors and the gender-coded name estimate was below its floor. All three absolute-gap intervals overlapped their corresponding floor intervals. This run therefore leaves above-floor decision divergence unestablished. Interval overlap is a descriptive check. The exact paired tests below assess direction within each comparison.

| Oriented bare comparison | Pairs | First favoured | Other favoured | Exact McNemar p | Mean score, first minus other [95% CI] |
|---|---:|---:|---:|---:|---:|
| Kazakh-language name vs others | 28 | 2 | 0 | 0.500 | +0.7 [−1.8, +3.8] |
| Russian-language name vs others | 26 | 0 | 1 | 1.000 | +0.2 [−1.7, +2.1] |
| English-language name vs others | 26 | 0 | 1 | 1.000 | −1.0 [−4.2, +1.9] |
| Male-coded name vs female-coded name | 40 | 0 | 4 | 0.125 | −0.4 [−1.2, +0.6] |
| Flagship vs regional university | 40 | 1 | 0 | 1.000 | +2.5 [+1.1, +4.1] |

Each language row uses only pairs involving that language. Those comparisons share pairs. The flips descriptively favoured Kazakh-language and female-coded names, reversing my predicted English-language and male-coded advantages. The flagship score difference was directional in this sample, with a sign-test p of 0.002 and a score-gap interval above zero. It is an exploratory score signal. The tier's shortlist flip rate equalled the same-tier floor, and the absolute score-gap intervals overlapped. Several comparisons were examined, and independent data would help assess whether the directional score signal repeats.

With 40 pairs, the notebook's two-sided McNemar test at 0.05 needs at least 6 one-way discordances (15.0%) when none go the other way, 8 (20.0%) with 1 in the other direction, or 10 (25.0%) with 2 in the other direction. Smaller or more balanced directional differences can go undetected. The floors test alternative strings within the same name language and gender coding or within the same university tier, using a fixed layout and greedy decoding. Their scope is the sampled perturbations. Prompt layout and wording, additional identity strings, other hardware, other models and real applicant distributions remain unmeasured. A stronger follow-up would use more independent pairs, varied names and institutions, prespecified contrasts and a separate order probe.

**After the harness.** All five groups had 0/40 flips (0.0%, 95% CI [0.0%, 8.8%]) and 0/40 score differences. Each group's mean absolute gap was 0.00 [0.00, 0.00] and the signed mean was +0.00 [+0.00, +0.00]. The pair members received identical prompts and met the same routing rules, so agreement was built into this comparison. The profile-level result was substantial. Shortlists fell from 356 to 276 and rejects rose from 44 to 124. Of 400 outcomes, 82 changed, with 81 shortlist-to-reject and 1 reject-to-shortlist. Of 400 profiles scored in both runs, 175 changed score, with a mean absolute change of 14.54 points among those 175. Removing four input lines changes both information and layout, so this design cannot attribute those changes to any one field or establish which decisions improved.

The inclusive review band (45, 45) covered 34/400 scored baseline profiles (8.5%). It escalated 0/400 (0.0%) after blinding, below both the baseline workload and my prediction. Each measured configuration used 400 model calls. Separately, the harness refused 5/6 boundary probes before generation, and 0/400 clean measured profiles were wrongly refused.

## 2. Who is affected

Male-coded names were shortlisted in 80.0% of the gender-coded pairs versus 90.0% for female-coded names. The four discordant pairs all advantaged the female-coded member. In the language pairs the descriptive shortlist rates were 92.3% for Russian-, 96.2% for English- and 96.4% for Kazakh-language names. The one university-tier flip favoured the flagship member, and the regional group had the lower mean score. These splits suggest who would bear the risk if the patterns recur. The wide intervals and floor comparisons leave the direction and size of real-world disparities uncertain. The labels are name signals and fictional tiers. The exercise contains neither verified demographic identities nor independent eligibility judgments.

In any discordant pair, if both applicants should have advanced, the one screened out could lose aid or the chance to continue studying and have to spend time asking for review. If both should have been rejected, the wrongly shortlisted applicant could take a scarce review or scholarship slot from another qualified applicant. The applicant who is erroneously shortlisted may still have to invest time before a later reversal. The 81 newly rejected profiles in the harness run make review access material even when pair outcomes match. This experiment cannot determine which of their recommendations should be reversed.

The fixed intake can delay eligible applicants whose institution is missing or whose name falls outside the format, including people whose records are already difficult to reconcile. People who expect exclusion may never apply. Reviewers and applicants bear the consequences of any later queue backlog, and the fund bears the staffing, appeals and trust costs. Reusing first-stage scores in later rankings can carry an early disadvantage forward. Across cycles, even a difference below this run's detection threshold could affect who remains in the applicant pool.

## 3. Professional responsibility

As the developer, I am responsible for checking pair construction, prompt exclusions, refusal call counts and the completeness of the audit trail. The submitted run shows identical blinded prompts within pairs and zero model calls on the five refused probes. The deterministic preflight separately exercised the review branches. I would disclose that the real-run review workload was zero and that the observed increase in rejections has no independent accuracy check. Before live use I would test with a representative held-out sample, independently reviewed merits and revised review routing. A scope bypass, missing log, or review workload outside an agreed and staffed range would halt automatic routing until investigated.

The fund owns the merit criteria, applicant notices, the appointment and training of reviewers, corrections and appeals, and final award decisions. If the fund sought to remove the consent or purpose gate to save staff time, I would show the actual probe evidence, document the scope breach, and keep those cases on a staffed intake route. The size of the post-blinding outcome shifts and the observed absence of review are reasons to require human approval before a recommendation can close an actual application.
