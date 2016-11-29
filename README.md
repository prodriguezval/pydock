# PyDock

#### A docker environmet to work with python


## Installation

* Clone the project
```bash
git clone git@github.com:prodriguezval/pyodock.git
```
* Edit the file workspace/requirements.txt to add your own dependencies

* Build the containers

```bash
docker-compose up -d workspace
```

### Integration with Python sources

* The folder structure must be like this: 
```
development (main folder)
    - pyodock (pydock folder)
    - my_python_sources_folder_name (your project folder)
```

## Usage

inside the pydock folder execute:

```bash
docker exec -it pydock_workspace_1 bash
```

 and use it like a regular linux bash


Any contribution will be welcome :)
 
Enjoy.
