
## **1. Setup**

```bash
git clone https://github.com/suriya030/Evaluation-test.git
cd .\Evaluation-test\Task-IV
conda create -n ddpm-pytorch python=3.8
conda activate ddpm-pytorch
pip install -r requirements.txt
```
**NOTE** : Compatible versions of CUDA toolkit and CuDNN should be downloaded for GPU support. 
## **2. Usage**
```ddpm-pytorch.ipynb``` contains all the necessary scripts for training, generating new images, and computing FID score. Notebook is organised into multiple SECTIONS as given below:

<p align="center">
  <img src="https://github.com/user-attachments/assets/1c973356-5a53-4a84-99dd-a62356b6bc8e" width="400" alt="Code snippet" style="margin-right:40%;">
</p>

- For **training** (from scratch): Run **SECTIONS 1, 2, 3, 4 and 5** (Refer above figure).  
  **NOTE**: Delete the following file before training: `.\Evaluation-test\Task-IV\default\ddpm_ckpt.pth`.
    
- For **generating new samples**: Run **SECTIONS 🚨FILL HERE**  
  **NOTE**: Trained DDPM model Checkpoint should be present at `.\Evaluation-test\Task-IV\default\`, by default I have included my trained DDPM model checkpoint there `ddpm_ckpt.pth`.
    
- For **FID score calculation**: Run **SECTIONS🚨 FILL HERE**  
  **NOTE**: Trained DDPM model Checkpoint should be present at `.\Evaluation-test\Task-IV\default\`, by default I have included my trained DDPM model checkpoint there `ddpm_ckpt.pth`.


