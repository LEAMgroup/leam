Landuse Evolution and Assessment Model (LEAM)
=============================================

LEAM is a spatial model used to forecasts how population, employment and land
use will change across large regions and over time. LEAM imports model inputs
from a broad array of data sources and produces a collection of raster maps
representing location, quantity, and time of specific population and employment
changes. These results can easily be aggregated into any type of geographic
boundaries, from counties to traffic analysis zones to neighborhoods, to
provide an estimate of annual change in population and employment for next 30
or 40 years in each area. Using modified model inputs allows LEAM to forecast a
wide variety of potential development scenarios.


Installation
============
LEAM is a complex spatial model with many dependencies including 3rd party
packages such as GRASS, GDAL, and various python modules as well as several
custom modules currently available on GitHub. The installation document
included in this repository gives the overview of the installation process.
Specific details for each of the required modules can be found in the module's
repository.

LEAM was developed under Ubuntu and instructions found here reflect that
environment.  But LEAM should be fairly portable to other systems including
MS Windows.  If you attempt to install LEAM under a different OS please let us
know.

1. Install development environment (compilers, mpi, git, various python
   modules, etc) since we'll need to be able to compile things. I don't have a
   canonical list of dependancies.  

    sudo apt-get update
    sudo apt-get install build-essential autoconf automake git
    sudo apt-get install python-dev python-pip python-gdal
    sudo pip install requests


2. Install GIS tools.  Primarily GRASS and GDAL, you'll need the development
   environment too.  Looks like the most recent Ubuntu support them as packages
   which will make things easier.

    sudo apt-get install grass grass-doc grass-dev

3. Clone GRASS modules from the
   [grass-modules](https://github.com/LEAMgroup/grass-modules) repository.
There are some script modules and some that need to be compiled with GRASS
environment.  Then these need to be installed or placed in the path.



4. Clone GLUC from the [gluc repository](https://github.com/LEAMgroup/gluc),
   build, and copy the binary to /usr/local/bin.  It will need to have an MPI
compiler installed to build it.


5. Clone LEAM from the [leam repository](https://github.com/LEAMgroup/leam).  A
   this stage you should be able to run the LEAM model using the sample
   configuration file provided. This configuration will pull the required data
   from LEAMgroup servers and run a simple scenario.  Results will be stored
   locally as part of the GRASS mapset rather being pushed back to LEAMgroup.

6. (optional) If the LEAM model will be run automatically using the LEAMgroup
   Planning Portal front-end then clone the job monitor from for the
[job-monitory repository](https://github.com/LEAMgroup/job-monitor) and install
it.

