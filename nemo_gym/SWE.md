# SWE RL with NeMo Gym + verl

## Setup

1. Clone NeMo Gym, checkout branch `cmunley/swe-public`.
2. Run `Gym/responses_api_agents/swe_agents/setup_scripts/openhands.sh` once from a login node.
3. Copy `config.env.example` to `config.env` and fill in `VERL_ROOT`, `NEMO_GYM_ROOT`, `RESULTS_ROOT`, `HF_HOME`, `WANDB_API_KEY`, `WANDB_USERNAME`.
4. Set `dataset_path` in your agent config yaml. Use the SWE-Gym split for non-zero reward with a base instruct model:
   `/lustre/fsw/portfolios/llmservice/users/cmunley/super-datasets/datasets/swe_swegym_only_with_sifs.jsonl`

## Launch

```bash
sbatch submit_swe_4b_8n_200t.sh
# or
sbatch submit_swe_1n.sh
```
