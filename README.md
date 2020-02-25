# CpuSet
Cpuset is a Python application

yum install python-pip
yum install python-configparser
yum install python-future
yum install glances 
======================

https://github.com/lpechacek/cpuset

python setup.py install

running install
running build
running build_py
running build_scripts
running install_lib
running install_scripts
changing mode of /usr/bin/cset to 755
running install_data
running install_egg_info
Removing /usr/lib/python2.7/site-packages/cpuset-1.6-py2.7.egg-info
Writing /usr/lib/python2.7/site-packages/cpuset-1.6-py2.7.egg-info
 
3 cpusets

root => present in all configurations and contains all cpus (unshielded)
system => contains cpus used for system tasks - the ones which need to run but aren't "important" (unshielded)
user => contains cpus used for "important" tasks - the ones we want to run in "realtime" mode (shielded)

pidof python2
ps -p 8285 -o comm=

==================================================

ps aux |grep ssh | awk '{print $2}' | tr '\n' ','

===================================================

cset shield -c 1-3
cset shield                => Ayırdığn CPU nun ayrıntısını gösterir
cset shield --shield -v
cset shield --unshield -v
cset shield --reset

cset proc --list --set=koray_cpuset --verbose
=============================================

 https://www.server-world.info/en/note?os=CentOS_7&p=cgroups&f=1


 yum -y install libcgroup libcgroup-tools
 systemctl start cgconfig
 systemctl enable cgconfig

yum install kernel-doc

===========================

lscgroup

systemd-cgls

==================================
nproc --all     => Print CPU Adet

lscpu | egrep 'Model name|Socket|Thread|NUMA|CPU\(s\)'



==================================

taskset - retrieve or set a process's CPU affinity

===================================


blkio	It limits on input/output access to and from block devices.

cpu	It uses the scheduler to provide cgroup tasks access to the CPU.

cpuacct	It generates automatic reports on CPU resources.

cpuset	It assigns individual CPUs on a multicore system and memory nodes to tasks.

devices	It allows or denies access to devices by tasks.

freezer	It suspends or resumes tasks in a cgroup.

hugetlb	It limits to use HugeTLB.

memory	It limits on memory use by tasks and generates automatic reports on memory resources.

net_cls	It tags network packets with a class identifier (classid).

net_prio	It provides a way to dynamically set the priority of network traffic per network interface.

perf_event	It identifies cgroup membership of tasks and can be used for performance analysis.

pids	It limits number of processes.
