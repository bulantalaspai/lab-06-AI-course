# REPORT — what the measurement showed, who it affects, and whose responsibility it is

## 1. Measurement read-out

**PENDING GPU RESULTS.** The notebook is prepared for the matched-pair run. The baseline, harness comparison and refusal probes require the same Qwen checkpoint on a Colab T4. No model measurements or confidence intervals are available from the local control tests.

The same-group name floor measures sensitivity to replacing a name within its language group and gender coding. The same-tier university floor measures sensitivity to choosing a different institution within its tier. Pair members share the same layout. The floors therefore cover these particular changes to irrelevant strings under greedy decoding. They leave prompt order, alternate wording, new identity strings, other hardware, real applicant distributions and other models untested.

The baseline read-out gives pair counts, flip rates with Wilson intervals, directional discordance and exact McNemar tests, signed score gaps and mean absolute score differences with bootstrap intervals. Directional significance and comparison with a floor answer different questions. Scores can move in both directions even when their signed mean cancels. Overlapping marginal confidence intervals are only a rough comparison. The exact-test detection counts describe the minimum directional discordance under specified conditions and do not establish a general guarantee of power. A stronger follow-up would rerun with a larger independent sample, more varied names and institutions, preregistered contrasts and a separate prompt-layout probe.

With the harness enabled, each matched pair has identical model text and identical policy inputs for routing. Pair agreement checks that enforced information boundary. Profile-level changes combine removed fields, altered layout and human-review routing.

## 2. Who is affected

**PENDING GPU RESULTS.** The observed directional discordances and their uncertainty are needed to identify which name or university groups were more often disadvantaged within the measured pairs. An inconsistent pair shows that two profiles with equal merit received different treatment. With no independent eligibility labels, the experiment cannot locate the correct decision or count genuinely wrong awards.

A wrongly rejected applicant can lose financial support and access to study or have to spend scarce time pursuing a correction. A wrongly shortlisted applicant still faces later review and may consume a slot or interview that an equally qualified applicant needed. Applicants whose institution is absent from the catalogue or whose name fails its syntax can incur delays before the merits are read. People who expect exclusion may never apply and are absent from the experiment. Human reviewers absorb the escalations and can create a new bottleneck. The fund bears the costs of overruns, appeals and reputational damage. If a screening output becomes a later ranking input, an early flag can follow a person beyond the first decision. Across cycles, small recurring disparities can compound even when there is too little evidence to distinguish them from a floor in this run.

## 3. Professional responsibility

As the developer, I have to verify pair invariants, confirm that identity and eligibility fields never enter the blinded prompt, and test that disallowed requests make no generation call. I also have to check that parser failures and blank rationales route to a person, every outcome receives a record and every comparison can be reproduced from the saved notebook. Local deterministic checks exercise control behavior. Deployment evidence would require the real model run, independent evaluation of errors and subgroup effects, and workload measurements with actual reviewers. I would disclose the two floor definitions, interval widths, lack of ground-truth outcomes and the difference between equal pair prompts and evidence of equitable screening.

The deploying fund owns eligibility and merit policy, appoints trained reviewers with authority to reverse a recommendation, provides an accessible correction and appeal channel and decides when service levels require more staffing. I would stop automated screening if an out-of-scope request reached the model, records were missing, or review cases exceeded the staffed queue. If the fund asked to remove a verified gate for throughput, I would document which failures would recur and keep those cases on human intake until the fund could meet the conditions that justified automation.
