# pub.dinosaur.is

my public [scuttlebot](https://github.com/ssbc/scuttlebot) server

## setup

- create fresh DigitalOcean dokku image
- point pub.dinosaur.is to IP address
- `ssh root@pub.dinosaur.is`, then run the following

```
# dokku apps:create pub
# dokku docker-options:add pub deploy "-p 127.0.0.1:8008:8008"
# sudo -u dokku mkdir -p ~dokku/.data/pub
# dokku docker-options:add pub deploy "-v /home/dokku/.data/pub:/app/data"
# dokku docker-options:add pub run "-v /home/dokku/.data/pub:/app/data"
# dokku config:set pub ssb_host=pub.dinosaur.is ssb_pub=true ssb_local=false ssb_gossip__connections=5 ssb_path=/app/data
```

- `git remote add deploy dokku@pub.dinosaur.is:pub`
- `cat ~/.ssh/id_rsa.pub | ssh root@pub.dinosaur.is "sshcommand acl-add dokku dinosaur"`
- `git push deploy master`

## invite

to be announced
