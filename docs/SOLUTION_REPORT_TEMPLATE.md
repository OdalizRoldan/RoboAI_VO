# Solution Report

**Candidate Name:** Odaliz Rojas
**Date:** 21/01/26
**Time Spent:** 

---

## Executive Summary

[2-3 sentences summarizing your key findings and improvements]

---

## Issues Discovered

### Issue 1: The formula used for calculating speed lacks precision due to a minimum number of steps and a large time interval.

**Category:** Physics
**Severity:** Medium

**Description:**
The accuracy of the final speeds and positions is inaccurate due to the initial values ​​of these two parameters, where:

`dt = 0.05`
`max_steps = 100`

If greater precision is desired, the value of `max_steps`, which is the number of iterations in which the calculation is performed, must be increased, and the value of `dt` must be decreased accordingly, since one value depends on the other.

The values ​​used for the following test are:

`dt = 0.05`
`max_steps = 2500`

**How I Found It:**
Based on Gabriel's explanation about the accuracy of numerical methods on the computer and seeing the results of the simulations where the final position of the cars is very far from the target, it was concluded that the calculation of the final speed and position is imprecise, so the described parameters were modified.

**Evidence:**
In the evaluative graphs of the first test, it could be seen that the model's predictions were 0%, on the other hand, in the evaluative graphs, it can be visually seen that the final positions are far from the proposed target.

---

### Issue 2: In the split of the dataset for validation and training, the IDs of each data point were being randomly mixed, which caused the training and validation data to be very similar, resulting in data leakage.

**Category:** Data

**Severity:** High

**Description:**
Looking at the training and validation logs, very low losses can be seen, as well as a very similar value between training and validation, which is an indication of data leakage.

To fix this, the predefined function `split_dataset_by_trajectory` was used to split the data by trajectory ID, ensuring true randomness between the training and validation data.

**How I Found It:**
The logs and training graph showed the closeness of the values ​​and, furthermore, after an analysis regarding how the data is being split, it was concluded that it is not being mixed correctly.

**Evidence:**
These logs show that the losses are low:

```bash
Epoch  10: train_loss=0.000155, val_loss=0.000153
Epoch  20: train_loss=0.000115, val_loss=0.000111
Epoch  30: train_loss=0.000102, val_loss=0.000109
Epoch  40: train_loss=0.000093, val_loss=0.000104
Epoch  50: train_loss=0.000088, val_loss=0.000087
Epoch  60: train_loss=0.000065, val_loss=0.000070
Epoch  70: train_loss=0.000061, val_loss=0.000067
Epoch  80: train_loss=0.000060, val_loss=0.000058
Epoch  90: train_loss=0.000057, val_loss=0.000061
Epoch 100: train_loss=0.000048, val_loss=0.000050
```

What is ideal, however, in the evaluation there was an accuracy of 0.

---

### Issue 3: [Title]

[Add more as needed...]

---

## Solutions Implemented

### Solution 1: [Title]

**Addresses:** Issue #[X]

**Approach:**
[What did you change and why?]

**Code Changes:**
[point to the commit or PR for this change and which code to run and how]

**Results:**
[Metrics or images before and after]

---

### Solution 2: [Title]

[Add more as needed...]

---

## Results Summary

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Idealized Robot Success Rate | X% | Y% | +Z% |
| Realistic Robot Success Rate | X% | Y% | +Z% |
| Mean Final Distance (Realistic) | X m | Y m | -Z m |
| Validation Loss | X | Y | -Z% |

---

## Debugging Process

### Initial Hypotheses
1. [First thing you suspected]
2. [Second hypothesis]
3. [...]

### Experiments Run
1. **Experiment:** [Description]
   **Result:** [What you learned]

2. **Experiment:** [Description]
   **Result:** [What you learned]

### Dead Ends
[Approaches that didn't work and why — this is valuable information!]

---

## Remaining Issues

[What problems did you identify but not fix? Why?]

1. **Issue:** [Description]
   **Why Not Fixed:** [Time constraints / complexity / need more information]

---

## Future Improvements

If I had more time, I would:

1. [Improvement 1]
2. [Improvement 2]
3. [...]

---

## Side Quests Completed

- [ ] Docker Container
- [ ] Other: [Specify]

---

## Reflections

### What I Learned
[Key takeaways from this challenge]

### What I Would Do Differently
[If starting over, what approach would you take?]

---

## Appendix

### A. Visualizations

[Include relevant plots, trajectory comparisons, etc.]

### B. Full Experimental Results

[Detailed metrics if not included above]

### C. References

[Any resources you consulted]
