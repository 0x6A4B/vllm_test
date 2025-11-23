## Docker asennetaan pakettien hallintaan

```bash
# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
```

```bash
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


## Kun Docker on asennettu

Verify docker service is running and enabled (starts on reboot)
```bash
sudo systemctl status docker
```

Verify it works with hello-world (optional)
```bash
sudo docker run hello-world
```

export hugginface api token
```bash
export HF_TOKEN='token'
```

```bash
scp docker-compose_vllm_mini.yaml root@94.237.118.101:/root/
```


vllm mini
```bash
# start
docker compose -f vllm_mini.yaml up -d

# view logs
docker compose -f vllm_mini.yaml logs -f

#stop
docker compose -f vllm_mini.yaml.yml down


```

vllm poro
```bash
# start
docker compose -f vllm_poro.yaml up -d

# view logs
docker compose -f vllm_poro.yaml logs -f

#stop
docker compose -f vllm_poro.yaml.yml down
```



