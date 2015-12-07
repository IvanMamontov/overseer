# Overseer
Git clone of the overseer library http://sosoa.inf.unisi.ch/Instruments/Overseer

Overseer is a set of tools simplifying access to real-time measurement of low-level information such as 
Hardware Performance Counters (HPCs), IPMI sensors, and Java VM internal events. 
Overseer supports functionalities like HPC-management, process/thread affinity settings, 
RDTSC timers, child-processes tracing, power-consumption and temperature monitoring, etc. 
Both the C/C++ and Java languages are supported. 

Based on libpfm4 and Linux kernels (2.6.31+), Overseer does not require specific patches or additional modules, thus offering a better solution for distributed and dynamic configurations not demanding administrator modifications to the underlying system.

# Requirements

Overseer requires the following development tools to be installed and configured on the targeted systems:
- libpfm http://perfmon2.sourceforge.net/
- hwloc http://www.open-mpi.org/projects/hwloc/
- freeipmi http://www.gnu.org/software/freeipmi/

For Fedora 22 and later versions:
```bash
sudo dnf install -y libpfm hwloc freeipmi libpfm-devel hwloc-devel freeipmi-devel
make
sudo make install
```

Runtime libraries are installed to ```/usr/local/bin``` by default. Edit makefiles if your Linux distribution doesn't follow this standard. 
To access Overseer functionalities from Java, include the ```overseer.jar``` file that is available in the ```/src/java/``` directory.
Also don't forget about Shared Library Management(http://www.cyberciti.biz/tips/linux-shared-library-management.html) and register your dynamic libraries in ```/etc/ld.so.conf``` or use LD_LIBRARY_PATH environment variable.

# Examples

See examples folder.
