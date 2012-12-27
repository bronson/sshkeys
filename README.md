This script manages SSH keys by keeping an authorized_hosts file
on a set of servers in sync.  To use it, just fork this repo, add some
keys to authorized_keys, and run ./setup HOST once for each host that
you want to manage.  Anyone with ssh access can manage the keys.

Since all keys are public, in theory it doesn't matter if this repo is
disclosed to attackers.  Still, best to keep it private.


### To authorize someone

First, have them generate an ssh key

    ssh-keygen -b 4096

add that user's key to the authorized_keys file

    cat ~/Documents/id_rsa.pub >> authorized_keys

Then commit and run `./deploy`.


### To remove someone's authorization

Delete the key from authorized_keys, then commit and run `./deploy`.


### To set up a new server

run `./setup username@mynewhost.example.com`


## License

Pain-free MIT: http://en.wikipedia.org/wiki/MIT_License

Upstream Project: https://github.com/bronson/sshkeys
