# Enabling SSH with authentication key instead of password

1. Generate a public key on the client machine
...Optionally add a password to it.
...```shell
...ssh-keygen
...```

2. Install the public key on the server
...Since Mac lacks the `ssh-copy-id` utility, use this workaround:
...```shell
...cat ~/.ssh/id_rsa.pub | ssh user@host "mkdir -p ~/.ssh; cat >> ~/.ssh/authorized_keys"
...```

Now you should be able to login on the server without password entry, simply issuing `ssh user@host`.
