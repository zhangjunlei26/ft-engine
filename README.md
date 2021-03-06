TokuDB
======

TokuDB is a high-performance, transactional storage engine for MySQL and
MariaDB.  For more details, see our [product page][products].

This repository contains the MySQL plugin that uses the [TokuKV][tokukv]
core.

There are also patches to the MySQL and MariaDB kernels, available in our
forks of [mysql][mysql] and [mariadb][mariadb].

[products]: http://www.tokutek.com/products/tokudb-for-mysql/
[tokukv]: http://github.com/Tokutek/ft-index
[mysql]: http://github.com/Tokutek/mysql
[mariadb]: http://github.com/Tokutek/mariadb


Building
--------

The `scripts/` directory contains a script that can be used to build a
working MySQL or MariaDB with Tokutek patches, and with the TokuDB storage
engine, called `make.mysql.bash`.  This script will download copies of the
needed source code from github and build everything.

To build MySQL with TokuDB 7.0.1:
```sh
scripts/make.mysql.bash --git_tag=tokudb-7.0.1
```

To build MariaDB with TokuDB 7.0.1:
```sh
scripts/make.mysql.bash --git_tag=tokudb-7.0.1 --mysql=mariadb-5.5.30
```

Before you start, make sure you have a C++11-compatible compiler (GCC >=
4.7 is recommended) and the libraries and header files for valgrind,
zlib, and Berkeley DB.  On Centos, `yum install valgrind-devel zlib-devel
libdb-devel`, on Ubuntu, `apt-get install valgrind zlib1g-dev libdb-dev`.
If your default compiler is not new enough, you can pass a different one:
`scripts/make.mysql.bash --cc=gcc47 --cxx=g++47`.


Contributing
------------

Please report bugs in TokuDB here on github.

We have two publicly accessible mailing lists:

 - tokudb-user@googlegroups.com is for general and support related
   questions about the use of TokuDB.
 - tokudb-dev@googlegroups.com is for discussion of the development of
   TokuDB.

We are also available on IRC on freenode.net, in the #tokutek channel.


License
-------

TokuDB is available under the GPL version 2.  See [COPYING][copying]

The TokuKV component of TokuDB is available under the GPL version 2, with
slight modifications.  See [README-TOKUDB][license].

[copying]: http://github.com/Tokutek/ft-engine/blob/master/COPYING
[license]: http://github.com/Tokutek/ft-index/blob/master/README-TOKUDB
