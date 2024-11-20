# Complete Guide to Managing Conda Virtual Environments in JupyterLab

## Initial Setup

### 1. Creating and Activating Environment
Open JupyterLab terminal and run (it can be done from command line as well, if paths are set properly):
```bash
# Create new environment
conda create -n <envname>

# Activate the environment
conda activate <envname>
```

### 2. Essential Package Installation
```bash
# Install pip if not present
conda install pip

# Install ipykernel for Jupyter integration
pip install --user ipykernel

# Register the kernel with Jupyter
python -m ipykernel install --user --name=<envname>
```

## Using the Environment

### Accessing in Jupyter Notebook
1. Launch JupyterLab
2. Create new notebook
3. Click "Kernel" > "Change Kernel"
4. Select your `<envname>` from the kernel list

### Installing Additional Packages
```bash
# Activate environment first
conda activate <envname>

# Install packages using pip
pip install <package-name>

# Or using conda
conda install <package-name>
```

## Best Practices

### Package Installation Priority
1. Try `conda install` first
2. If package not available in conda, use `pip install`
3. Always install packages while environment is activated

### Environment Management Commands
```bash
# List all environments
conda env list

# List packages in current environment
conda list

# Export environment
conda env export > environment.yml

# Create environment from yml file
conda env create -f environment.yml
```

## Cleanup and Maintenance

### Remove Kernel from Jupyter
```bash
# List installed kernels
jupyter kernelspec list

# Remove specific kernel
jupyter kernelspec uninstall <envname>
```

### Remove Environment
```bash
# Deactivate environment first
conda deactivate

# Remove environment and all its packages
conda env remove --name <envname>
```

## Common Issues and Solutions

### Package Conflicts
- If experiencing conflicts, try installing packages in this order:
  1. Core packages via conda
  2. Additional packages via pip
- Use `conda clean --all` to clean cache if facing installation issues

### Kernel Not Showing
If kernel doesn't appear in Jupyter:
1. Ensure ipykernel is installed
2. Re-run kernel installation command
3. Restart JupyterLab

## Best Security Practices

### Virtual Environment Location
- Default location: `~/opt/anaconda3/envs/<envname>`
- Keep sensitive data and credentials outside environment directory
- Use environment variables for sensitive information

### Package Verification
```bash
# View package details before installation
conda search <package-name>

# Verify installed package
conda list <package-name>
```

## Environment Backup

### Creating Backup
```bash
# Export environment with exact versions
conda env export > environment.yml

# Export only manually installed packages
conda env export --from-history > environment.yml
```

### Restoring Environment
```bash
# Create environment from backup
conda env create -f environment.yml
```

Remember:
- Always activate environment before installing packages
- Keep environment.yml file for backup
- Regularly update packages within environment
- Clean up unused environments and kernels to save space
