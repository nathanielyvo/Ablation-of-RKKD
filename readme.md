**The Abaltion of RKKD**
---
The following figures show the curve of kl loss, ranking loss, and test acc during the optimization process of kd and kd+ranking loss. In the kd method, ranking loss is only used for calculation and does not participate in gradient calculation.

- **Consistent Optimization Direction** When ranking loss is not added into the gradient calculation, ranking loss still decreases as KL divergence decreases. This is because KL divergence requires linear alignment of teacher and student logits, which to some extent will help them have more consistent ranking results. But when ranking loss is added into the gradient calculation, ranking loss decreases faster and more consistent ranking results are obtained in the end. This also shows that ranking loss can pay more attention to the value of the channel with smaller channel output, so more consistent ranking results can be obtained.
- When ranking loss is added, the KL divergence decreases faster, and after the learning rate is reduced, the KL divergence drops to a lower value.Therefore, it can be shown that in the early stage of optimization, ranking loss constrains the kl divergence to decrease. It prevents kl divergence from entering the suboptimum case, so the kl divergence decreases faster. At the same time, in the later stage of optimization, ranking loss will not interfere with the decrease of kl divergence, so the kl divergence decreases further and reaches a smaller value.
- Also, because ranking loss make students pay more attention to information with smaller channels, students have stronger generalization and can perform better on the test set.
- 
*Figure 1. The ranking loss*
![image](https://github.com/nathanielyvo/Ablation-of-RKKD/blob/main/rk_loss.jpg)
![image](https://github.com/nathanielyvo/Ablation-of-RKKD/blob/main/kd_loss.jpg)
![image](https://github.com/nathanielyvo/Ablation-of-RKKD/blob/main/test_acc.jpg)
