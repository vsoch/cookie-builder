Continuous Builder Cookie Cutter Template
=========================================

Do you want to generate a [repo2docker](https://www.github.com/jupyter/repo2docker)
notebook for data science to create a reproducible container that others can pull
and use your notebook? This cookie cutter template will get you started quickly!

# Usage

```bash
pip install cookiecutter
cookiecutter https://www.github.com/vsoch/cookie-builder
```

## Step 1. Generate Codebase

### Quick Start
You don't need to download or clone anything - you can just install cookiecutter 
(a Python package on pip) and then run the `cookiecutter` command!

1. Install cookiecutter

```bash
pip install cookiecutter
```

```bash
cookiecutter https://www.github.com/vsoch/cookie-builder
```

You can also clone the repository, edit the [cookiecutter.json](cookiecutter.json)
file within, and type cookiecutter /path/to/cookie-builder to generate the new repository.

## Step 2. Add Dependencies

Once you've generated the codebase, write your Python dependencies in the `requirements.txt`
file. You should include versions if possible! To see what version of a particular software
you are using for a Python installation, you can use pip freeze. For example:

```bash
# show all dependencies
pip freeze

# search for tensorflow
pip freeze | grep tensorflow
```

## Step 3. Write Notebook
Then you can write [jupyter notebooks](http://jupyter.org/install) to your heart's content
in the repository! When you are done, follow the instructions in the [continuous build](https://github.com/binder-examples/continuous-build) repository
to connect your repository to CircleCI, define a Docker Hub repository, and then commit and push
to trigger the automated build. That's it! When you finish and the container is deployed, you should
be able to run it, again per [instructions here](https://repo2docker.readthedocs.io/en/latest/deploy.html). Or simply:

```bash
docker pull <ORG>/<NAME>
docker run -it --name repo2docker -p 8888:8888 <ORG>/<NAME> jupyter notebook --ip 0.0.0.0
```
