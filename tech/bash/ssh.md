#mosh

install bosh in server and client

1. client OS X
2. server Ubuntu

###Server (non root)

	./configure --prefix=/home/jzhou/mosh_install; make; make install

set in bash_profile

###Client

	mosh xxx@host.name.edu --server=/home/jzhou/mosh_install/bin/mosh-server -p portNum


#general way

	1. ssh-keygen -t rsa
	2. copy the pub to the server: ~/.ssh/authorized_keys

#ssh hostname

	Change the
	HostName, Port, User in ~/.ssh/config
