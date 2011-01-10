Phing Build Scripts
===================

Install
-------
$ cd $project_root
$ git submodule add git://github.com/phostr/phing-build-common.git build/common
$ cp build/common/examples/build.xml .
$ cp build/common/examples/build.properties .

Edit both build.xml and build.properties as needed ..

Usage
-----

Available targets:

$ phing ci
$ phing build
$ phing package -Ddeb.signwith=<Gpg Key Id>
$ phing package-zip
$ phing package-deb -Ddeb.signwith=<Gpg Key Id>
$ phing publish-deb
$ phing clean

Example build.xml
-----------------

<?xml version="1.0"?>
<project name="example" basedir="." default="main">
	<property file="build.properties" />
	
	<import file="build/common/build.xml" />

	<!-- Copy and edit the build, package-deb and package-zip targets
	     from build/build-common.xml if needed -->

</project>

Example build.properties
------------------------

app.name = example
app.description = Example Project
app.version = 1.0
deb.control.maintainer = info@example.com
deb.control.homepage = http://www.example.com
deb.maintainer.name = Example
deb.maintainer.email = info@example.com
deb.distribution = example
deb.control.section = main
deb.control.architecture = all
deb.control.depends =
deb.control.builddepends = debhelper (>= 7.0.50~)
deb.control.predepends =
deb.control.recommends =
deb.control.suggests =
deb.control.conflicts =
deb.control.provides =
publish.dupload.target = my-dupload-target
