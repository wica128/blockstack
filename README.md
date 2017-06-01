# blockstack
scripts for working with blockstack


## Install on Debian
### Blockstack-core 

Make sure that pip is for python 2.7!!

```
apt-get install -y python-pip python-dev libssl-dev libffi-dev rng-tools libgmp3-dev
pip install pyparsing
pip install blockstack --upgrade
```

On debian we have a little issue, when we try to run blockstack:
```
  File "/usr/local/lib/python2.7/site-packages/jsontokens/key_loading.py", line 14, in <module>
    from cryptography.hazmat.backends.multibackend import MultiBackend
ImportError: No module named multibackend
```

It looks like we do not need this, but then again I can be wrong.

Edit file /usr/local/lib/python2.7/site-packages/jsontokens/key_loading.py and remove the line
`from cryptography.hazmat.backends.multibackend import MultiBackend`


### First run aka setup.

`blockstack info`

Now we get some questions, and I use the default.

If you get something like this, we are ready

```
Saving configuration to /home/wica/.blockstack/client.ini
{
    "advanced_mode": false, 
    "cli_version": "0.14.1.7", 
    "consensus_hash": "79f96das6340675f9799053", 
    "last_block_processed": 464230, 
    "last_block_seen": 468246, 
    "server_alive": true, 
    "server_host": "node.blockstack.org", 
    "server_port": 6264, 
    "server_version": "0.14.1.5"
}
```


And test it.
```blockstack whois wica128.id```


