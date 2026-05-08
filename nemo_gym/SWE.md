# SWE RL with NeMo Gym + verl

## Setup

1. Clone NeMo Gym, checkout branch `cmunley/swe-public`.
2. Run `Gym/responses_api_agents/swe_agents/setup_scripts/openhands.sh` once from a login node.
3. Clone this repo (`cmunley1/verl-recipe`), checkout branch `cmunley/swe-nemogym-recipe`.
4. Copy `recipe/nemo_gym/config.env.example` to `config.env` and fill in `VERL_ROOT`, `NEMO_GYM_ROOT`, `RESULTS_ROOT`, `HF_HOME`, `WANDB_API_KEY`, `WANDB_USERNAME`.
5. Update paths in `recipe/nemo_gym/configs/swe_4b_8n_200t.yaml`:
   - `nemo_gym_root` / `config_paths`: your Gym clone path
   - `dataset_path`: your dataset JSONL (tested SWE-Gym)
   - `container_formatter`: your SIF paths

## Launch

```bash
# 4B model, 8 nodes
sbatch recipe/nemo_gym/submit_swe_4b_8n_200t.sh

# 30B instruct, 16 nodes
sbatch recipe/nemo_gym/submit_swe_30b_16n_32k.sh
```
