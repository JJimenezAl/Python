# Anaconda Comandos



## Desactivar entorno

```bash
conda config --show | grep auto_activate_base
```
 
To set it false
```
conda config --set auto_activate_base False
source ~/.bashrc
```
To reactivate set it to True
```
conda config --set auto_activate_base True
source ~/.bashrc
```

## Podemos deshabilitarlo y que se vuelva a cargar la siguiente vez que iniciemos sesion con el usuario

```
conda deactivate
```



## Busqueda por plataforma

https://anaconda.org/search


## Actualizacion

```
conda update -n base -c defaults conda
```


## Instalacion Sw
```
conda install python=3.6
numpy
numpy 1.8*
numpy 1.8.1
numpy >=1.8
numpy ==1.8.1
numpy 1.8|1.8*
numpy >=1.8,<2
numpy >=1.8,<2|1.9
numpy 1.8.1 py27_0
numpy=1.8.1=py27_0
```
### Añadir canal de sw
```
conda config --add channels https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda/linux-ppc64le/
```
### Eliminar caches y paquetes descargados

```
conda clean -a 
```


## Virtuales

[Web Oficial] (https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

```
conda info --envs
```

### Crear entornos

```
conda create --name v1 --no-default-package
conda create --name v2 --no-default-packages
```
Una vez creados

```
(base) [nashpc01@servpwr901 ~]$
conda activate nombre_entorno
(v1) [nashpc01@servpwr901 ~]$
```
Deja de verse base y aparece el nuevo entorno

### Eliminar entornos

```
conda remove -n nombre --all
```
### Exportar/importar Entornos

```
#Activar primero el entorno 
conda env export > environment.yml
conda env create -f environment.yml
```

Otras opciones
```
conda list --explicit > spec-file.txt

conda create --name myenv --file spec-file.txt

conda install --name myenv --file spec-file.txt
```




###integrarlos los envs en jupyter
```
Conda install nb_conda
```



There is also another way. You can directly use the python executable from environment in ExecStart like this:

ExecStart=/path/to/conda/envs/my_env_name/bin/python /path/to/executable

For my CentOS server where I'm using miniconda the path is:

ExecStart=/root/miniconda3/envs/test_env/bin/python3 /root/test.py


## Uninstall
### Opcion 1

Quitar la carpeta con rm -rf (generalmenet donde se ha ejecutad el script /anaconda3
MIrar parth como se ha quedadopor si hay que quitar la ruta

### Opcion 2
```
conda install anaconda-clean
```

Remove all Anaconda-related files and directories with a confirmation prompt before deleting each one:
```
anaconda-clean
```
Or, remove all Anaconda-related files and directories without being prompted to delete each one:
```
anaconda-clean --yes
````




























