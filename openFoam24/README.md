# drp-spack-config
CCI DRP spack configuration and scripts for building OpenFoam-org 2.4.0
with the GNU GCC compilers and OpenMPI.

## contents

compilers.yaml - compiler list

config.yaml - global config

modules.yaml - hierarchical layout for lua modules

packages.yaml - system installed packages

README.md - this file

setupSpack.sh - env needed for executing spack commands

spack.yaml - list of packages to install

## setup

```
git clone git@github.com:spack/spack.git spack
cd !$
git checkout v0.14.2
# create the environment
spack env create openFoam24
spack env activate openFoam24
# copy the yaml files into the openFoam24
cp /path/to/the/dir/with/the/yaml/files/* var/spack/environments/openFoam24
# copy the compiler yaml file into the spack etc dir
cp /path/to/the/dir/with/the/yaml/files/compilers.yaml etc/spack/.
```

On a system with network access create a mirror of repos

```
//create mirrorSpecs.txt with specs of the needed packages
spack mirror create -d spack-mirror -f mirrorSpecs.txt
```

then rsync it to the CCI and add it to the repo

```
spack mirror add packages file::///path/to/mirror/dir
```

## resuming work in an environment

```
source /gpfs/u/software/dcs-spack-src/dcs-spack-config/setupSpack.sh
spack env activate openFoam24
```

