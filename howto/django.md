# django

## sqlite版本不对

* Step 1 - Updating SQLite ver. On CEntos server
```bash
wget https://www.sqlite.org/2021/sqlite-autoconf-3340100.tar.gz
tar zxvf sqlite-autoconf-3240000.tar.gz
./configure
make
sudo make install
```

* Step 2 - Recompiling Python to Use the New SQLite
```bash
wget https://www.python.org/ftp/python/3.9.2/Python-3.9.2.tgz
tar xvf Python-3.9.2.tgz 
cd Python-3.9.2
./configure --enable-optimizations
export LD_LIBRARY_PATH="/usr/local/lib
make
make altinstall
```

* 测试
```
python3.9 -c "import sqlite3; print(sqlite3.sqlite_version)"
```

* sample site
```bash
django-admin startproject mysite
python3.9 manage.py runserver
```
