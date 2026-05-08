# SWE RL with NeMo Gym + verl

## Setup

1. Clone NeMo Gym, checkout branch `cmunley/swe-public`.
2. Run `Gym/responses_api_agents/swe_agents/setup_scripts/openhands.sh` once from a login node.
3. Clone `cmunley1/verl` (fork of `verl-project/verl`), checkout branch `cmunley/swe-nemogym-recipe`.
4. Copy `recipe/nemo_gym/config.env.example` to `config.env` and fill in `VERL_ROOT`, `NEMO_GYM_ROOT`, `RESULTS_ROOT`, `HF_HOME`, `WANDB_API_KEY`, `WANDB_USERNAME`.
5. Update paths in `recipe/nemo_gym/configs/swe_4b_8n_200t.yaml`:
   - `nemo_gym_root` / `config_paths` → your Gym clone path
   - `dataset_path` → your dataset JSONL (tested with SWE-Gym)
   - `container_formatter` → your SIF paths

## Launch

```bash
sbatch submit_swe_4b_8n_200t.sh
# or
sbatch submit_swe_30b_16n_32k.sh
```
