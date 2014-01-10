# Multi-machine

Create a hostfile:

    machine1:2
    machine2:2
    machine3:3

Sure it's more convenient to use **mpdboot**. To do this, just first set up a file **mpd.hosts** in some directory, with the names of the machines on which you want daemons to be running; list the network names of the machines, one line per machine.

Then type:

    mpdboot --totalnum=3 --verbose // here 3 is the number of machines

Then go to the program in the first machine and type:

    mpirun -n 10 ./run // here the 10 is the number of processes
