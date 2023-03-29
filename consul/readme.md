## Start consul 

### Bootstrap and import Tokens
```
consul acl bootstrap | tee consul/config/consul.bootstrap

export CONSUL_HTTP_TOKEN=<TOKEN>
cd consul/config
consul acl policy create -name agent-internal -rules @acls/agent_internal.hcl
consul acl policy create -name server-policy -rules @acls/server_policy.hcl
consul acl policy create -name vault-ro -rules @acls/vault_ro_policy.hcl
consul acl policy create -name vault-rw -rules @acls/vault_rw_policy.hcl
consul acl policy create -name prometheus -rules @acls/prometheus_ro.hcl
```

### update anonymous token with the policy

```
acl token update -accessor-id <Anonymous Token ID> -append-policy-id <Policy ID>
```

