# wandb

archive notes:
/home/bearceb/mnt/QTIM/22-2198/MICCAI_Fractionation/README.md

> Some inspiration (# https://github.com/wandb/server/issues/66)
A guide to using the free tier of wandb

## Find some scratch space
```bash
SUBFOLDER=bb-10_25_2024 # example
cd /scratch90/$SUBFOLDER
```

```bash
git clone git@github.com:QTIM-Lab/wandb-deploy-example.git
cd wandb-deploy-example
```

Check if your co-workers have one running so you can change the port if needed.
```bash
docker ps | grep wandb
```

Ex:
> 8080 is consumed at the moment, use diff port below
```bash
bearceb@ophlapps04:/scratch90/bb-10_25_2024/wandb-deploy-example$ docker ps | grep wandb
5348dc0d2184   wandb/local              "/sbin/my_init"          3 hours ago     Up 3 hours   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp                       wandb-local
```

## Launch
> Assuming no one is running a wandb
```bash
pyenv activate wandb_3.12.3 # need wandb package installed `pip install wandb`
```

```bash
USER=bearceb
CONTAINER_NAME=wandb-$USER
PORT=8080
DOCKER_VOLUME=$CONTAINER_NAME
docker run -d --name $CONTAINER_NAME -p $PORT:8080 -v $DOCKER_VOLUME:/vol wandb/local
```
Check it:
`http://localhost:8080/`
![root.png](root.png)
Click or enter: `http://localhost:8080/login` -> redirect -> `http://localhost:8080/signup`
![log_in_or_sign_up.png](log_in_or_sign_up.png)

## Make account or use QTIM's

![qtim-wandb.png](qtim-wandb.png)

See `qtim_one_time_license.md` for our license for a free tier
```bash

TBDDDDDDDDDDDd I'm working on it
```