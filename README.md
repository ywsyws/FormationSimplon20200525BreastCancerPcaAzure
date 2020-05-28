# FormationSimplon20200525NannyScrappy

# FormationSimplon20200525

## Note to set up docker
#### to build an image
```docker build -t <image name> .```

#### to run a container
```docker container run -it --name <container name> -p 8002:5000 -v "$(PWD):/workspace" -d <image name>```
e.g.: docker container run (--rm) -it --name "azure-ml" -p 8001:5000 -v "$(PWD):/workspace" (-d) jupyter-python
explaination:  	       containers name /  hostPC port: service port in container / $(PWD) = projects directory

#### to execute the container in bash
```docker exec -it <container name> bash```

#### start jupyter notebook in the containter
```jupyter notebook --port=5000 --NotebookApp.password='' --NotebookApp.token='' --no-browser --ip=0.0.0.0 --allow-root```

#### launch jupyter notebook in navigator
localhost:8002

## Consignes
- A partir d’un notebook en local, créer un workspace ML Azure comme ce qu’on a fait avec Laurent mardi (en utilisant le SDK)
- Dans le notebook, importer le dataset breast cancer de sklearn (https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html), qui est un dataset de classification (objectif est de prédire si la tumeur est ['malignant', 'benign'])
- En utilisant une Experiment (comme mardi), faites varier dans les différents run et de manière conjointe
    - Le nombre de composantes conservées dans l’ACP
	- Le temps nécessaire pour entraîner le modèle
	- L’accuracy sur le test set
		 
- Vous enregistrerez ces différents éléments avec run.log
- Visualisez les résultats de l’Experiment sur le portail Azure