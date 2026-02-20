# Conda & Mamba Cheat Sheet

A concise reference for creating and managing environments with **Conda** and **Mamba**.

## Quick Take

- **Conda** is the standard tool that ships with Anaconda/Miniconda; it is reliable and always available.
- **Mamba** is a drop-in replacement for `conda` that is **much faster** at solving environments and downloading packages.
- Use **Mamba** when you care about speed; use **Conda** when you want the default, most widely documented behavior.

If you have `mamba` installed, you can usually replace:

- `conda` → `mamba`

## Install Mamba (Recommended)

```bash
conda install -n base -c conda-forge mamba
```

## Environment Basics

### Create an Environment

```bash
# With Conda
conda create -n myenv

# With Mamba (same command, faster)
mamba create -n myenv
```

You are **not required** to specify Python when creating an environment. If you omit it, the environment starts empty and you can add packages (including Python) later.

### Activate / Deactivate

```bash
conda activate myenv
conda deactivate
```

### List Environments

```bash
conda env list
# or
conda info --envs
```

### Remove an Environment

```bash
conda env remove -n myenv
```

## Install / Update Packages

### Install Packages

```bash
# Install into active environment
conda install numpy pandas

# Or in a specific environment
conda install -n myenv numpy pandas
```

### Update Packages

```bash
conda update numpy
conda update --all
```

### Search Packages

```bash
conda search scikit-learn
```

## Channels

Channels are package repositories that Conda searches when installing or updating packages. You can install from a specific channel with `-c`.

Popular channels:

- `defaults` (the official Anaconda channel, used by default)
- `conda-forge` (community-maintained, very broad coverage)

### Use conda-forge (popular and up-to-date)

```bash
conda install -c conda-forge black
```

## Export / Recreate Environments

### Export to YAML

```bash
conda env export -n myenv > environment.yml
```

### Create from YAML

```bash
conda env create -f environment.yml
```

## Faster Solves and Downloads

If Mamba is installed, prefer:

```bash
mamba install ...
mamba create ...
mamba update ...
```

Mamba uses a faster solver and parallel downloads, so it is often **significantly quicker** than Conda on large environments.

## Troubleshooting

### Reset a Broken Environment

```bash
conda env remove -n myenv
conda create -n myenv
```

### Clean Cache

```bash
conda clean --all
```

## Notes

- Prefer `mamba` for speed; use `conda` if you want the default tool everywhere.
- The commands are intentionally identical between `conda` and `mamba`.
