# Mordern Operating System

## chp2 PROCESS

### PROCESS

* pseudoparallelism & multiprocessor
* A process is just an instance of an executing program, including the current vallues of the program counter, gegisters and variables.
* daemons
* execve
* process talbe / process control blocks    

### THREAD

#### Thread Usage

##### reason

* the ability for the parallel entities to share an address space and all of its data among themselves
* lighter weight than processes, easier(i.e., faster) to create and destory.
* though yield no performance gain, when substantial computing or I/O, having threads allows these activities to overlap.

#### The Classical Thread Model

##### based on two independent concepts

* resource grouping
* execution

##### each thread has its own stack

