# dockerethinkdb
Docker  container with RethinkDB inside

`make server` is the intended use,

you then should be able to link another container like so:

```
docker run --name some-app --link dockerethinkdb:rdb -d application-that-uses-rdb
```

you’ll need an inventory file in /etc/ansible/hosts with some lines like:

```
dockerethinkdbhost ansible_ssh_port=22 ansible_ssh_host=127.0.0.1 ansible_ssh_user=root

[dockerethinkdb]
dockerethinkdbhost
```

there are also the `make boostrap` and `make docker` recipes these will bootstrap ansible (i.e. install python and ansible) and install docker on a debian host respectively

[Please check out my blog for other associated miscellanea:](http://joshuacox.github.io/)
[joshuacox.github.io](http://joshuacox.github.io/)
