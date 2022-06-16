# msa-config-server


## How to configure SSH key for authenticate git repository
1. Generate key
   ssh-keygen -t ecdsa -b 256 -m PEM -f config_server_key_pem_ecda.rsa
   
2. Add sshkey to GitHub's account from settings/SSH keys with content from config_server_key_pem_ecda.rsa.pub 

3. Add application.properties
   
   spring.cloud.config.server.git.uri=git@github.com:thongmz/test-config.git
   spring.cloud.config.server.git.ignore-local-ssh-settings=true
   spring.cloud.config.server.git.skip-ssl-validation=true
   spring.cloud.config.server.git.default-label=main
   spring.cloud.config.server.git.private-key=\
   -----BEGIN EC PRIVATE KEY-----\n\
   MHcCAQEEIM4v+m7xq8cgdvRBx3x8Fm4iHRL3yUs+FZ+6pst8tCRdoAoGCCqGSM49\
   AwEHoUQDQgAESYZGZf+sO6ZbBg8NPm9dgv3m/kvkeDx+zYZHhwU2eaOwQck4j1cv\
   KUth/1cCIXvR1bYJIR8+OySXn3rD/SMhJA==\
   -----END EC PRIVATE KEY-----