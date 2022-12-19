# Pacemaker VRRP deploy
![CI workflow](https://github.com/randsw/nginx-vrrp-cluster/actions/workflows/vrrp-cluster-setup-ci.yaml/badge.svg)

## Deploy

### Start vagrant VM

`vagrant up`

### Deploy HA mongodb cluster

`ansible-playbook -i inventories/vrrp-cluster/hosts.yml vrrp-deploy.yml`
