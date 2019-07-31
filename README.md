# Fight Food Waste deployement

## Setup Ansible

Download roles:

```sh
ansible-galaxy install -r requirements.yml
```

## Web server setup

Only manual action required: installing Caddy on the server:

```sh
# curl https://getcaddy.com | bash -s personal
```

Setup OS config and middlewares:

```sh
ansible-playbook pb-middleware.yml
```

It will setup MariaDB, PHP, Node, Caddy and more.

## Laravel apps setup

Create valid `.env.collects` and `.env.services` locally.

Deploy laravel apps:

```sh
ansible-playbook pb-laravel-app.yml -e app_name=collects
ansible-playbook pb-laravel-app.yml -e app_name=services
```
