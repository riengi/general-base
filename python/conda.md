# Anaconda / Conda / Miniconda

## Create environment from yaml configuraiton
```
conda env create -f environment.yaml
```

## Conda list environments
```
conda env list
```

## Activate environment
```
conda activate <env_name>
```

## Deactivate environment 
```
conda deactivate
```

## Update environment 
```
conda env update -f environment.yaml
```

## Update with pruning (removing not specified packages)
```
conda env update -f environment.yaml --prune
```

## Update named environment 
```
conda env update --name myenv -f env.yaml
```

## Update conda
```
conda update -n base -c defaults conda
```

