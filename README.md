# Attribution Patching

Method for identifying circuits in transformer models.
First order approximation for activation patching, first results show at least 2 OOM speedup compared to activation patching. 


## First Milestone
Achieve substantial speedup for activation patching algorithm:
1. First pass with attribution patching: Identifying a superset of heads, which would have been identified with activation patching over all nodes. Getting rid of a large number of irrelevant heads.
2. Then apply activation patching to the remaining heads.

Main research question: Can activation patching identify a superset of heads, which are identified by activation patching?
First toy model: Induction heads


## Second Milestone
Do the same thing with path patching, ACDC-style.