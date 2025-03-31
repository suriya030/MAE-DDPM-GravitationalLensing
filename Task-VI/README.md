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

### **2. Usage**

#### pre-training MAE
 - ```mae-pretrain.ipynb``` contains the necessary scripts for pre-training MAE ( from scratch ). 
  **Note** : Download the folder named ```dataset``` from the [🚨drive🚨](), and place it at the location ```.\Evaluation-test\Task-VI\.``` .

#### linear-probing MAE
 - ```mae-linearprobe.ipynb``` contains the necessary scripts for linear probing MAE . 
  **Note** : Download the folder named ```saved_models``` from the [🚨drive🚨](), and place it at the location ```.\Evaluation-test\Task-VI\.``` .

#### finetuning MAE for classification
 - ```Task-VIA\mae-finetune-VIA.ipynb``` conatains the necessary scripts for finetuning MAE for classification on dark matter sub-structure . 
 **Note** : Download the folders named ```dataset``` and ```saved_models``` from the [🚨drive🚨](), and place both of them at location ```.\Evaluation-test\Task-VI\Task-VIA\.``` .

#### finetuning MAE for Super-Resolution
 - ```Task-VIB\mae-finetune-VIB.ipynb``` conatains the necessary scripts for finetuning MAE for super-resolution. 
 **Note** : Download the folders named ```dataset``` and ```saved_models``` from, the [🚨drive🚨](), and place both of them at location ```.\Evaluation-test\Task-VI\Task-VIB\.``` .

### **3. Dataset and Implementation**
- It has been discussed in the respective notebooks.

### **4. Results**

**Pre-training results**

Loss curve obtained during pre-training MAE and, linearprobing accuracy which is used to evaluvate the learned representations are shown below,

<div style="display: flex; justify-content: center; align-items: flex-start;">
  <!-- Image Section -->
  <div style="margin-right: 20px;">
    <img src="./figures/loss_curve.png" alt="Loss Curve" width="300">
  </div>

  <!-- Table Section -->
  <div>
    <table>
      <thead>
        <tr>
          <th>Model</th>
          <th style="text-align: right;">Linear Probing Accuracy (%)</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>example1</td>
          <td style="text-align: right;">76.3</td>
        </tr>
        <tr>
          <td>example2</td>
          <td style="text-align: right;">78.5</td>
        </tr>
        <tr>
          <td>example3</td>
          <td style="text-align: right;">74.2</td>
        </tr>
        <tr>
          <td>example4</td>
          <td style="text-align: right;">75.0</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>


We've set up a side-by-side comparison to show how our model rebuilds an image using its learned representations. On the left, you'll see the original image, and on the right is the model's reconstructed version, and in the middle is the masked original image.

<div style="text-align: center;">
  <img src="figures/prediction.png" alt="Descriptive text" width="700">
</div>

**Classification results**

We have obtained a Top 1 test accuracy : **92.61 %**

( train - 60,000 images , val - 9,000 images , test - 18000 iamges )












### **5. Discussion**


