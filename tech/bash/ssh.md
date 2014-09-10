#mosh

install bosh in server and client

1. client OS X
2. server Ubuntu

###Server (non root)

	./configure --prefix=/home/jzhou/mosh_install; make; make install

set in bash_profile

###Client

	mosh xxx@host.name.edu --server=/home/jzhou/mosh_install/bin/mosh-server -p portNum

