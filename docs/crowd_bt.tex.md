# What?

So Gavel is based on the premise that judges, called annotators, are best suited to pairwise comparisons,
answering if hack A is better than hack B. This leads to an interesting problem since we must recover a
global ordering of the hacks from the different orderings of each judge. Furthermore, the paper tries to
measure the reliability of the judges since some of them could be biased.

In this document, I hope to make a readable and somewhat complete summary of the paper. It's organized as
follows:
- The problem description.
- The old solution.
- The update to the solution.
- Inefficiencies and getting rid of them.

# The Problem

Given a set of pairwise comparisons of hacks per judge, find a global ranking of all the hacks.
The paper, hence this summary, uses $A \succ B$ to mean that $A$ is preferred over $B$.
There are some issues that can already arise: one judge can say $A \succ B$ while another reports
$B \succ A$, or one judge can have $A \succ B \succ C$ while another has $C \succ A$.
