# docker
A platform for running, building and shipping Application

## Some times your Code work in one machine and doesnot on the other
One or more file is missing (It is not included as the part of your Deployment)
Software version mismatch (Lets say your application needs node version 14 but the target machine is running node version 9)
Different Configuration Settings (environment setting are different)

## Docker comes as rescue
With Docker we can package our application with everything it needs anywhere, in any machine

For Example your Project needs
Node 14
Mongo 4
App

All this will be included in your application package
With this package run it in any machine that has docker: Its going to work on Dev test and production machine

## There is more 
If any new member joins they donot have to spend half a day setting up the project they can simply tell docker to 
bring up your application
docker-compose up

Docker will download and run this dependencies in the Isolated environment called container

The beauty of Docker is container

THis isolated environment allows multiple application using different version of Software side by side

One application may use node version 14 and other may use node version 9

All these machine can run side by side without messing with each other


## One more Benefit
If you are done with one application then we can remove all its dependenceies in one go
lets say you do not need version 9 then you can remove all dependencies

docker-compose down --rmi all

Docker Helps us consistently build, run and ship applications

## Container
An Isolated environment for Running your application 

## Virtual Machine
An Abstraction of a machine(physical hardware), so we can run several virtual machine on your physical machine
For Example We have mac on this machine we can run two virtual machine Windows and other running linux this we do that with the tool called Hypervisor

Hypervisor: In Simple is a software used to create and manage virtual machine

## Hypervisors Available
Virtual Box
Vmware
Hyper-v(Windows only)
They are cross platform so that they can run on windows, mac-os and linux

## What is the benefit of using virtual machine
Run Applications in Isolation
On same physical machine you can have two virtual machines
Each running completely different application and each have the exact dependencies it needs

Virual Machine 1                            Virtual Machine 2
App 1                                       App 2
Node 14                                     Node 9
Mongo 4                                     Mongo 3

All this application are running on same machine but in different isolated environments

## Probelm with the VM model
Each VM system needs a full-blown os: which needs to be licensed, patched and monitored
Slow to Start because the entire operating system have to be loaded just like starting your computer
Other Problem is that they are resourse intensive because each virtual machine: Each virtual machine take the slice of the actual physical harware resources like cpu memory and disk space

So if you have 8 giga bytes of Memory, that needs to be divided into different virtual machines

Ofcourse how much memory to allocate to virtual machine and at the end of the we have limit of number of VMS
we can run on a machine usal.y handfull or we will run out

## Containers
Allows running mutiple apps in Isolation
Are lightweight: they do not need a full operating system
all containers share and use operating system of the host
We need to license patch and monitor single operating system
start quickly
Need less hardward resources


Single Host can run tons of container side by side

## Docker Architecture
It uses the client server architecture
Technically container is just the process running on your compouter

image.png

All container use the kernel of the host
A kernal manages application and hardware resources: Just like engine of the car

Windows: Window+ linux: We can run both windows and linux containers Windows 10 comes with custom built linux kernel
Linux: We can run only linux containers
Mac os: Has its own kernel Docker on Mac uses lieght weight virtual machine to run linux containers


## Installing latest version of Docker
Link: https://docs.docker.com/get-docker/
Version: docker version to check the version

## Lets talk about developement workflow
Application it doesnot matter what find of application it is we take that application and dockerise it 
Which means we need to make the small change so that it can run by docker

How: We need to add the docker File
This docker file contains all the information needed to package the application into the image

This image contains everything the docker needs to run the application everything


Image will contain
A cut-down os
A run-time environment (eg node)
application files
third party Libararies
Environment variables and so one

So we create a docker file and give it to docker to packaging our application into an image

Once we have the image we tell docker to start the container using that image
Container: Its just a process because it has its own file system provided by the image

Our application gets loaded inside the container process and this is how we run our application local development machine


Image goes to the Registory a Hub of the Image files and then can be run on any machines
Dev-------------------------> Registory------------------------------> Test/Prod


## Important
We donot need to maintain long complex release document that have to precisely followed 
All the instruction of building the application are written in the docker file
With that we can package our application into an image and run it virtually anywhere































