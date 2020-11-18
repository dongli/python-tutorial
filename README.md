# How to setup a JupyterLab environment

First, you need to install `Docker` correctly. Then run `docker-compose` command to start a JupyterLab container:

```
docker-compose up -d
```
Then, find out the token:

```
docker-compose logs
```

Open `localhost:12000` in your browser, and input the token.
