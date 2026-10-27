# econ5200-lab08-hypothesis-testing
# Diagnosing Underpowered Studies and P-Hacking

## Objective
I studied how low statistical power, multiple testing, and p-hacking can lead to misleading conclusions in hypothesis testing.

## Methodology
- I analyzed a pilot study with 15 people per group and calculated its statistical power.
- I estimated the sample size needed to reach 80% power.
- I applied the Benjamini-Hochberg correction to 20 subgroup tests.
- I simulated 1,000 repetitions of 20 tests when all null hypotheses were true.
- I wrote my own Benjamini-Hochberg function and compared its results with statsmodels.
- I compared Welch's t-test, Yuen's trimmed t-test, and permutation tests on heavy-tailed earnings data.
- I simulated Brodeur's "camel" to see how p-hacking changes the distribution of significant results.

## Key Findings
- With 15 people per group, the pilot study had only 10.9% power against the true effect.
- About 222 people per group were needed to reach 80% power, and the adequately powered study gave p = 0.0012.
- After the Benjamini-Hochberg correction, 0 of the 20 subgroups remained significant.
- In the simulation, 65.8% of 1,000 replications had at least one p-value below 0.05, compared with 64.2% in theory.
- My Benjamini-Hochberg function matched statsmodels, and with two real effects planted, it flagged 2 subgroups.
- The four tests on heavy-tailed earnings data split according to whether they tested ordinary means or trimmed means, rather than whether they were parametric or permutation tests.
- In the p-hacking simulation, the share of significant results increased from 0.242 to 0.313, which was a 29.2% increase.
