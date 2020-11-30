# How to setup a JupyterLab environment

First, you need to install `Docker` correctly (follow the instructions
[here](https://www.docker.com/get-started)). Then you may set an environment
variable `WORK_HOME` to anywhere you need, but this directory should be in path
if you need the demo notebook files in `./data`. If you do not set one,
  `./data` will be used. After that, run `docker-compose` command to start a
  JupyterLab container:

```
$ docker-compose up -d
```

If you encounter difficulties to pull `jupyter/scipy-notebook` image, change
the DockerHub sources by following the instructions
[here](https://mirrors.ustc.edu.cn/help/dockerhub.html).

Then, find out the token:

```
$ docker-compose logs
Attaching to python-tutorial_worker_1
worker_1  | Executing the command: jupyter lab
worker_1  | [I 04:10:09.381 LabApp] Writing notebook server cookie secret to /home/jovyan/.local/share/jupyter/runtime/notebook_cookie_secret
worker_1  | [I 04:10:09.840 LabApp] JupyterLab extension loaded from /opt/conda/lib/python3.8/site-packages/jupyterlab
worker_1  | [I 04:10:09.840 LabApp] JupyterLab application directory is /opt/conda/share/jupyter/lab
worker_1  | [I 04:10:09.845 LabApp] Serving notebooks from local directory: /home/jovyan
worker_1  | [I 04:10:09.845 LabApp] Jupyter Notebook 6.1.4 is running at:
worker_1  | [I 04:10:09.845 LabApp] http://93d3a0f42722:8888/?token=27107196cd5ed307647e7547ac834e417d977620836eea5e
worker_1  | [I 04:10:09.845 LabApp]  or http://127.0.0.1:8888/?token=27107196cd5ed307647e7547ac834e417d977620836eea5e
worker_1  | [I 04:10:09.845 LabApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
worker_1  | [C 04:10:09.851 LabApp]
worker_1  |
worker_1  |     To access the notebook, open this file in a browser:
worker_1  |         file:///home/jovyan/.local/share/jupyter/runtime/nbserver-6-open.html
worker_1  |     Or copy and paste one of these URLs:
worker_1  |         http://93d3a0f42722:8888/?token=27107196cd5ed307647e7547ac834e417d977620836eea5e
worker_1  |      or http://127.0.0.1:8888/?token=27107196cd5ed307647e7547ac834e417d977620836eea5e
                                                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                                                             Copy this token
```

Open `localhost:12000` in your browser, and input the token.
