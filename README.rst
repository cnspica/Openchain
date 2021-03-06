Openchain Library
=================

About
-----

Library for creating blockchain networks.

**WARNING:** Currently library in **Beta** development status.
It's a concept of vision, not working library yet.

Author: Alexander Chaika <manti.by@gmail.com>

Source link: https://bitbucket.org/manti_by/openchain

Requirements:

- Base - Python 3.5+, ECSDA, LevelDB/Plyvel
- Development - Flake8, Coverage
- Examples - Docker, Tornado, PyP2P

Installation
------------

Install system libraries

    $ sudo apt install python3-dev libleveldb-dev

Install package from `PyPi <https://pypi.python.org/pypi/openchain>`_

    $ pip install openchain

Alternatively clone from `Bitbucket <https://bitbucket.org/manti_by/openchain>`_

    $ git clone git@bitbucket.org:manti_by/openchain.git

    $ cd openchain/

    $ python setup.py install

Environment variables
---------------------

- $DATABASE_PATH - path to store LevelDB files

Run the examples with Docker
----------------------------

    $ cd examples/

    $ docker build -t mantiby/openchain:latest .

    $ docker swarm init

    $ docker stack deploy -c docker-compose.yml openchain

Run unit tests and coverage
---------------------------

    $ mkdir -p /var/tmp/leveldb/test/

    $ export DATABASE_PATH='/var/tmp/leveldb/test/'

    $ python -m unittest discover -s openchain/tests/ -p '*_tests.py'

    $ coverage run -m unittest discover -s openchain/tests/ -p '*_tests.py'

    $ coverage report -m