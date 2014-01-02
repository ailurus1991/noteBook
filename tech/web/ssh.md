# Background
If we don't want to login our remote machine without typing the ip address, just edit content of file: /etc/hosts:

    111.111.111.111 linode

# Keys
We can generate a pair of ssh keys:

    ssh-keygen

Then we should copy and paste the content of _id_rsa.pub_ to the _authorized_keys_.

    cat id_rsa.pub > authorized_keys // just the meaning, cannot be executed


