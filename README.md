# Conda & Mamba Cheat Sheet


- `conda` → `mamba`

## Install Mamba 

```bash
conda install -n base -c conda-forge mamba
```

## Environment Basics

### Create an Environment

```bash
# With Conda
conda create -n myenv

# With Mamba (faster)
mamba create -n myenv
```

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

- `defaults` (the official Anaconda channel, used by default)
- `conda-forge` (community-maintained)

### Use conda-forge 

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

