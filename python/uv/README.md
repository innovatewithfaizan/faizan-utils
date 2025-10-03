````markdown
# ⚡ uv — Next-Gen Python Project & Package Manager

`uv` is a blazing-fast Python project and package manager written in Rust.  
It’s designed to unify tools like `pip`, `venv`, `pipx`, and `pyenv` into a single interface.

---

## 🔹 Why Use uv?
- Initialize new projects instantly
- Manage Python versions
- Install and lock dependencies
- Run tools (like `ruff`, `black`, `pytest`) without permanent installs
- Faster, modern replacement for pip/venv/poetry workflows

---

## 🚀 Common Commands I Use

### 1. Check uv Version
```bash
uv --version
````

---

### 2. Initialize a New Project

```bash
uv init my_project
```

Creates a fresh project directory with config files.

---

### 3. Manage Python Versions

```bash
# List available versions
uv python list

# Install a specific version
uv python install 3.12
```

---

### 4. Install Dependencies

```bash
# Install a package into the current project
uv add requests

# Install from requirements file
uv pip install -r requirements.txt
```

---

### 5. Run Tools Without Installing Globally

```bash
# Run ruff (linter) on demand
uvx ruff check .

# Run pytest without permanent install
uvx pytest
```

---

### 6. Tool Management

```bash
# Install a tool globally
uv tool install ruff

# Run it
ruff --version
```

---

## ✅ Real Workflow Example

My typical usage:

```bash
# 1. Start new project
uv init product_ass

# 2. Check if uv, python, git are available
python -m shutil which uv
python -m shutil which python
python -m shutil which git

# 3. Add dependencies
uv add pandas requests

# 4. Run checks without polluting global env
uvx ruff check .
```

---

## ⚡ Pro Tips

* Use `uvx` when you want to try tools quickly → no install overhead.
* Keep one `requirements.txt` or `pyproject.toml` → uv respects both.
* Pair with `shutil.which()` to auto-verify binaries in PATH.

---