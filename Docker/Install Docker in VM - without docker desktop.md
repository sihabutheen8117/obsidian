
Just run:

```
curl -fsSL https://get.docker.com | sudo sh
```


That’s it.

It will:

- Add repository
    
- Install Docker Engine
    
- Install CLI
    
- Install containerd
    
- Install buildx
    
- Install compose plugin
    

Automatically.

---
Allow running Docker without sudo:

```
sudo usermod -aG docker $USER
newgrp docker
```