**The Abaltion of RKKD**
---
The following figures show the curve of KL divergence, ranking loss, and test acc during the optimization process of KD and KD+ranking loss. In the KD method, ranking loss is only used for calculation and does not participate in gradient calculation.We can make the following conclusions about ranking loss from the figure:

- **Consistent Optimization Direction** As shown in the **Figure1**, when ranking loss is not added into the gradient calculation, ranking loss still decreases as KL divergence decreases. This is because KL divergence requires linear alignment of teacher and student logits, which to some extent will help them have more consistent ranking results. But when ranking loss is added into the gradient calculation, ranking loss decreases faster and more consistent ranking results are obtained in the end.
  
- **Help Optimize KL Divergence** As shown in the **Figure2**, when ranking loss is added, the KL divergence decreases faster, and after the learning rate is reduced, the KL divergence drops to a lower value.Therefore, it can be shown that in the early stage of optimization, adding rk loss can speed up the decline of KL loss, reduce its oscillation in the suboptimal range. At the same time, in the later stage of optimization, ranking loss will not interfere with the decrease of KL divergence, so the KL divergence finally optimize to a better position.

- **Better Test Accuracy** As shown in the **Figure3**, after adding ranking loss, the student model achieved leading accuracy on the test set at all stages of training. We can see that adding ranking loss can help the model converge and achieve better generalization and performance.
  
*Figure 1. The ranking loss curve when adding and not adding ranking loss to knowledge distillation for gradient calculation*

![image](https://github.com/nathanielyvo/Ablation-of-RKKD/blob/main/rk_loss.jpg)

*Figure 2. The KL divergence curve when adding and not adding ranking loss to knowledge distillation for gradient calculation*

![image](https://github.com/nathanielyvo/Ablation-of-RKKD/blob/main/KD_loss.jpg)

*Figure 3. The test accuracy curve when adding and not adding ranking loss to knowledge distillation for gradient calculation*

![image](https://github.com/nathanielyvo/Ablation-of-RKKD/blob/main/test_acc.jpg)
