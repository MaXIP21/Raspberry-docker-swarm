  ### Login hanging in clients but after refresh the login is complete:
  
  In the config/config.php add the overwritehost parameter if you are using https load balancer !!
  'overwritehost' => 'xxx.com', 'overwriteprotocol' => 'https', 'overwrite.cli.url' => 'https://xxx.com',