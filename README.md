webstorm-deb
=============

Build scripts to easily create a `.deb` package for WebStorm, based on [langemeijer/phpstorm-deb](https://github.com/langemeijer/phpstorm-deb).


Dependencies
------------

You will need the `devscripts` package installed in order to build the WebStorm `.deb` file:

```sh
apt-get install devscripts
```


Building
--------

* Download the `.tar.gz` file of WebStorm and place it in the root directory of this repo.

* Build the package with the following command:

```sh
debuild -us -uc -b
```


Installing
----------

Install the package with the `dpkg` command:

```sh
dpkg -i WebStorm...
```

New WebStorm Versions
---------------------

If the latest version of WebStorm is newer than the version listed in `debian/changelog`, you'll need to run the following command command to update the file:

```sh
dch -v <new-version-number> -m "New upstream version"
```

For example, if the latest version is 2016.1.2b, run the following:

```sh
dch -v 2016.1.2b -m "New upstream version"
```

You can then commit the change to `debian/changelog` and submit a pull request.
