### **1. Setup**

Run the following commands to clone the repo and, set up environment in your local system. Assuming you have already have miniconda / anaconda setup. 

```bash
git clone https://github.com/suriya030/Evaluation-test.git
cd .\Evaluation-test\Task-VI
conda create -n mae-pytorch python=3.12
conda activate mae-pytorch
pip install -r requirements.txt
```
**NOTE** : Compatible versions of CUDA toolkit and CuDNN should be downloaded for GPU support. 

--- 

### **2. Usage**

##### Pre-training MAE
 - ```mae-pretrain.ipynb``` contains the necessary scripts for pre-training MAE ( from scratch ). 
  **Note** : Download the folder named ```dataset``` from the [drive](https://iitracin-my.sharepoint.com/:f:/g/personal/r_ss_ee_iitr_ac_in/EiuMGqR0XUFKhZ9SXiVllR0BXvuCTIMz9tgAu3rf_p99YQ?e=U8PKlN), and place it at the location ```.\Evaluation-test\Task-VI\.``` .


##### Finetuning MAE for classification
 - ```Task-VIA\mae-finetune-VIA.ipynb``` conatains the necessary scripts for finetuning MAE for classification on dark matter sub-structure . 
 **Note** : Download the folders named ```dataset``` from the [drive](https://iitracin-my.sharepoint.com/:f:/g/personal/r_ss_ee_iitr_ac_in/EtwR26haTpZJmU7uk4a1yPkBBARunTTFudDHlt5Xp393jw?e=sZp7d0), and place it at location ```.\Evaluation-test\Task-VI\Task-VIA\.``` .

##### Finetuning MAE for Super-Resolution
 - ```Task-VIB\mae-finetune-VIB.ipynb``` conatains the necessary scripts for finetuning MAE for super-resolution. 
 **Note** : Download the folders named ```dataset``` from the [drive](https://iitracin-my.sharepoint.com/:f:/g/personal/r_ss_ee_iitr_ac_in/EsIYFsG1mwBMn8NJSBFMQjABde9cmCdT24lMRFDyK65H9w?e=WEqaQE), and place it at location ```.\Evaluation-test\Task-VI\Task-VIB\.``` .

---

### **3. Dataset and Implementation**
- For Pre-training MAE we have used 80-20 train-validation split of no substructure images .
- For Finetuning MAE-Encoder for classification of dark-matter substructure we used train-val-test split of 70-10-20.
- For Finetuning MAE-Encoder for super-resolution the split used is 80-10-10 for train-val-test.
  
For implimentation details refer the notebook.

---

### **4. Results**


**Pre-training Results**

The loss curve obtained during the MAE pre-training and the linear probing accuracy, which evaluates the learned representations, are shown below:

<p align="center">
  <img src="./figures/pretraining_loss_curve.png" alt="Pre-training Loss Curve" width="400">
</p>



Below is a comparison showcasing how our model reconstructs an image using its learned representations. The original image is on the left, the masked original image is in the center, and the reconstructed version by our model is on the right.

<p align="center">
  <img src="./figures/pretraining_pred_img.png" alt="Image Reconstruction Comparison" width="700">
</p>


**Note:** Artifacts in the unmasked regions of the **Predicted Reconstruction** arise because the loss function penalizes only the reconstruction of masked patches.


---

**Finetuning Pre-trained MAE-encoder for classifiation**

We achieved a **Top-1 Test Accuracy of 92.61%** ( Train-Validation-Test split 70-10-20 ) . Below are the ROC curve and the training-validation accuracy curves:

<table>
  <tr>
    <td align="center">
      <img src="./figures/taskVIA_roc_curve.png" alt="ROC Curve" width="400">
    </td>
    <td align="center">
      <img src="./figures/taskVIA_training_metrics.png" alt="Training-Validation Metrics" width="600">
    </td>
  </tr>
</table>


---

**Finetuning Pre-trained MAE-encoder for super resolution**

We propose a model leveraging a pretrained MAE encoder as a deep feature extractor, combined with a CNN-based shallow feature extractor. High-resolution image reconstruction is achieved through a sub-pixel convolutional layer. Our architecture is inspired by [SwinIR](https://arxiv.org/abs/2108.10257) by Lian et al. For more details refer the notebook.


| Model               | PSNR (dB) ↑ | SSIM ↑    | MSE ↓       |
|---------------------|-------------|-----------|-------------|
| Proposed model      | 40.23       | 0.966     | 0.000096    |

Below is an example illustrating how our model performs super-resolution on an image.

<p align="center">
  <img src="./figures/taskIVB_prediction.png" alt="Image Reconstruction Comparison" width="700">
</p>




---

### **5. Discussion**


