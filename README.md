# REINFORCEMENT LEARNING FINAL PROJECT – HEAT‑PUMP CHATBOT

# Team
**Team members**:
  - Elsa Farinella, SCIPER: 377583
  - Robin Faro, SCIPER: 370950
  - Marco Scialanga, SCIPER: 369469


This repository contains everything you need to reproduce the experiments from our course report.  The goal is to improve a GPT‑2‑Large heat‑pump Q\&A bot by aligning it with preference‑based reinforcement learning.

## CONTENTS

1. What the project does

2. Getting started

3. Folder guide

4. Typical workflow

5. Where to find results

---------------------------------------------------

1. WHAT THE PROJECT DOES
   • Curates a specialist Q\&A dataset on heat‑pump technology.
   
   • Builds a preference file (prompt, preferred answer, less‑preferred answer).
   
   • Fine‑tunes GPT‑2‑Large with two methods:
   – PPO‑style RLHF   → checkpoints/ppo\_\*
   – Direct Preference Optimisation (DPO) → checkpoints/dpo\_\*
   
   • Logs BLEU, ROUGE, BERTScore and reward curves to Weights & Biases.
   
   • Includes an optional RAG prototype that learns when to fetch external info.

2. GETTING STARTED
    
   a. Clone:   git clone [https://github.com/elsa-farinella/RL\_final\_project.git](https://github.com/elsa-farinella/RL_final_project.git)
   cd RL\_final\_project
   
   b. Env  :   conda create -n rl\_final python=3.10 -y
   conda activate rl\_final
   
   c. Deps :   pip install -r requirements.txt
   (optional) pip install wandb && wandb login
   
   d. Data :   open notebooks/build\_dataset.ipynb and run all cells.

3. FOLDER GUIDE
    
   data/        – raw & processed datasets 
   
   notebooks/   – build\_dataset, PPO‑1, DPO, RL‑Optimization 
   
   answers/     – model outputs for the test set
   
   checkpoints/ – saved models (created after training)

4. TYPICAL WORKFLOW

    1. Run build\_dataset.ipynb    → data/dpo\_dataset\_RL.json
       
    2. Run PPO‑1.ipynb            → checkpoints/ppo\_\*  + answers/ppo\_\*.json
   
    3. Run DPO.ipynb              → checkpoints/dpo\_\*  + answers/dpo\_\*.json
   
    4. Run RL‑Optimization.ipynb  to reproduce sweeps or tweak hyper‑params.

    Headless servers can execute notebooks with:
    jupyter nbconvert --to notebook --execute <notebook>.ipynb

5. WHERE TO FIND RESULTS
    
    • Metric tables appear at the end of each notebook.
   
    • Weights & Biases project: rl\_final\_project/\*
   
    • Best model: checkpoints/dpo\_final (see README inside that folder).

