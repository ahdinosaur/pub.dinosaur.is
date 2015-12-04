# pub.dinosaur.is

my public [scuttlebot](https://github.com/ssbc/scuttlebot) server

## setup

- create fresh DigitalOcean dokku image
- point pub.dinosaur.is to IP address
- `ssh root@pub.dinosaur.is`, then run the following

```
# dokku apps:create pub
# sudo -u dokku mkdir -p ~dokku/data/pub
# dokku docker-options:add pub deploy "-v /home/dokku/data/pub:/app/data"
# dokku docker-options:add pub run "-v /home/dokku/data/pub:/app/data"
```

- `git remote add deploy dokku@pub.dinosaur.is:pub`
- `cat ~/.ssh/id_rsa.pub | ssh root@pub.dinosaur.is "sshcommand acl-add dokku dinosaur"`
- `git push deploy master`

## invite

to be announced
