# Introduction

Sizing hardware for MISP deployment usually comes early in the project, without much view of what kind of sizing may be useful
nor what kind of usage volumes will be.
So we try to give here a simple HTML+Javascript-based sizing calculator to determine a basic hardware requirement for you.


# Basic information on MISP ressource usage

MISP is done to be deployable without consuming 8 GB of RAM when empty. 
You can run it on a 2GB machine, with limited disk such as 30GB.
For sure it can run on less, but then you will be limited later when samples are uploaded for example.

# Notions

Criterias that have impact on Disk + RAM + CPU from most impacting to less impacting:
* Count and size of attributes, objects, events, file attachements (most impact on: DISK)
* Correlation of event between each other (most impact on: CPU and Memory)
* Number of users (most impact on: not much)
