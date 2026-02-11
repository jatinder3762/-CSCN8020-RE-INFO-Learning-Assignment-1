# Assignment 1 — Reinforcement Learning (CSCN8020)



## Name: Jatinder Pal Singh    
## Student ID: 9083762

This workspace contains an interactive Jupyter notebook implementing solutions for four assignment problems and supporting files.

Files
- `Assignment-1.ipynb` — main notebook with all code and explanations.
- `requirements.txt` — inferred Python dependencies.
- `log/` — directory containing all generated log files:
  - `mc_episode_log.txt` — Monte Carlo episode log.
  - `problem3_iteration_log.txt` — Value iteration convergence log.
  - `problem3_agent_log.txt` — Agent movement trace for Problem 3.
  - `problem4_agent_path_log.txt` — Agent path for Problem 4.
  - `problem4_value_log.txt` — Value function convergence log for Problem 4.

Summary of the four problems

1) Problem 1 — Pick-and-Place Robot (MDP design)
   - Model the robot pick-and-place task as an MDP (S, A, P, R).
   - States: joint positions, joint velocities, gripper status.
   - Actions: motor torque commands per joint.
   - Reward: encourage fast, smooth, energy-efficient, successful placements.

2) Problem 2 — 2x2 Gridworld (Value Iteration, 2 iterations)
   - Small 4-state grid with deterministic transitions and per-state rewards.
   - Demonstrates two iterations of synchronous value iteration and policy extraction.

3) Problem 3 — 5x5 Gridworld (Value Iteration)
   - Full 5×5 grid with a goal (+10), penalty (grey) states (-5), and step cost (-1).
   - Implements synchronous and in-place value iteration, policy extraction, and runtime comparison.

4) Problem 4 — Off-policy Monte Carlo with Importance Sampling (Every-Visit, Weighted IS)
   - Uses the same 5x5 environment.
   - Implements behavior (random) policy, target (greedy) policy updates using weighted importance sampling, convergence graph, and policy visualization.

Prerequisites
- Python 3.10+ (a virtual environment is recommended).
- The workspace includes a virtual environment configured at:

  `./.venv/Scripts/python.exe`

Setup (recommended)
1. Open a terminal in the workspace folder (where `Assignment-1.ipynb` and `requirements.txt` live).

2. Activate the virtual environment.

- PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

- Command Prompt:

```cmd
.venv\Scripts\activate.bat
```

3. Install dependencies:

```bash
python -m pip install -r requirements.txt
```

Run the notebook interactively
1. Start Jupyter Notebook / JupyterLab:

```bash
python -m jupyter notebook
# or
python -m jupyter lab
```

2. Open `Assignment-1.ipynb` in the browser/VS Code and run the cells.

Run the notebook headlessly (execute all cells)

```bash
jupyter nbconvert --to notebook --execute Assignment-1.ipynb --output executed.ipynb
```

Notes & runtime parameters
- Log directory configuration: All log files are automatically stored in the `log/` directory. This is configured via the `LOG_DIR` variable and corresponding log file paths (e.g., `LOG_PROBLEM3_ITERATION`, `LOG_PROBLEM4_VALUE`) defined at the beginning of the notebook. If the directory doesn't exist, it will be created automatically when the notebook runs.
- Monte Carlo training parameters (in the notebook) such as `num_episodes` and `max_steps` can be adjusted before running the Monte Carlo section.
- The Monte Carlo routine writes progress to log files in the `log/` directory.
- If you prefer running the notebook programmatically, consider using `papermill` to parameterize runs (not currently in `requirements.txt`).

Troubleshooting
- If plotting fails in headless environments, ensure a display backend is available or use `%matplotlib agg` in code cells before plotting.
- If you see missing package errors, reinstall via `python -m pip install -r requirements.txt` using the workspace Python.

Contact
- If you want, I can: run the notebook here, pin exact dependency versions in `requirements.txt`, or add a short `run.sh` / `run.ps1` helper script. 
