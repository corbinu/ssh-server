*This is no longer being mantained if anybody wants to take over I would welcome it thanks!*

# SSH Server

Docker container for running OpenSSH server. Can be used in combination with [sshuttle](https://github.com/sshuttle/sshuttle) for creating a secure network connection to a docker cluster

## Running

It simply needs to be run with port 22 open

```
docker run -d --name ssh-server -p 22 corbinu/ssh-server
```

It only takes key auth so you can either copy your public key

```
cat ~/.ssh/id_rsa.pub | docker exec -i ssh-server /bin/bash -c "cat >> /root/.ssh/authorized_keys"
```

Or you can build a private image based on this one and add the key within your Dockerfile
