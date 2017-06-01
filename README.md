# blockstack
scripts for working with blockstack


## Install Debian
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
