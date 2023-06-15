# Attribution Patching

Method for identifying circuits in transformer models.
First order approximation for activation patching, first results show at least 2 OOM speedup compared to activation patching. 


## First Milestone
Achieve substantial speedup for activation patching algorithm:
1. First pass with attribution patching: Identifying a superset of heads, which would have been identified with activation patching over all nodes. Getting rid of a large number of irrelevant heads.
2. Then apply activation patching to the remaining heads.

Main research question: Can activation patching identify a superset of heads, which are identified by activation patching?

First toy model: Induction heads
- [ ] use ACDC library to set up activation patching on the induction task


## Second Milestone
Do the same thing with path patching, ACDC-style.


### Finding the relevant gradient for path patching with autograd.
Revision of autograd:
- List layer activations (outputs) in neural network in reversed topological order
- Find backward functions for all layers: $backward( x, out, grad_out = dL/d(out) ) = dL/d(x) $
![Alt text](<Screenshot 2023-06-15 at 11.49.55.png>)

