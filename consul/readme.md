## Start consul 

```
consul acl bootstrap | tee consul/config/consul.bootstrap

export CONSUL_HTTP_TOKEN=<TOKEN>
export CONSUL_HTTP_TOKEN=66997940-018a-bbf7-05d2-db8c40f50acf
cd consul/config
consul acl policy create -name agent-internal -rules @acls/agent_internal.hcl
consul acl policy create -name server-policy -rules @acls/server_policy.hcl
consul acl policy create -name vault-ro -rules @acls/vault_ro_policy.hcl
consul acl policy create -name vault-rw -rules @acls/vault_rw_policy.hcl
consul acl policy create -name prometheus -rules @acls/prometheus_ro.hcl


```