# Introduction

https://misp-project.org/MISP-sizer/

Sizing hardware for MISP deployment usually comes early in the project, without much view of what kind of sizing may be useful nor what kind of usage volumes will be.

So we try to give here a simple HTML+Javascript-based sizing calculator to determine a basic hardware requirement for you.

# Usage

serve local pages through local web server:
python2 -m SimpleHTTPServer 8000
open http://127.0.0.1:8000/

WARNING: Please note that file:// loading won't work.
That means that you can't use this directly by loading from the filesystem.
You need to get these files served through HTTP/HTTPS as there is some Javascript and executing it requires it to be served over HTTP/HTTPS.

# Basic information on MISP resource usage

MISP is done to be deployable without consuming 8 GB of RAM when empty. 
You can run it on a 2GB RAM machine, with limited disk such as 30GB.
For sure it can run on less, but then you will be limited later when samples are uploaded for example.

## Notions

Criterias that have impact on Disk + RAM + CPU + ... (from most impacting to less impacting):
* Count and size of attributes, objects, events, file attachements (most impact on: DISK)
* Correlation of event between each other (most impact on: CPU and Memory)
* Size of file attachments (most impact on: DISK)
* Number of REST API queries per minutes (most impact on: CPU and Memory)
* Number of displayed web page per minutes (most impact on: CPU and Memory)
* Number of users (most impact on: not much if they don't browse, already accounted in the webpage/mn metric)

## Limits

This is crude estimation based on many varying parameters that may be totally wrong for your usage or your organization.
So take these results with cautions.

## Limits Examples:

* If your attributes (alerts fields) are large strings for example, then the required disk size may be MUCH larger.
* If you plan to attach MANY LARGE FILES to each event, same, required disk size will be larger.
* If you have few users that do A LOT of REST API queries, required CPU and Memory will need to be larger. (tip: you might want to consider using zmq pubsub instead of REST API polling queries)

# About

This project was done in the course of a few hours, during the Hackathon + Training of March 2018 at CIRCL / SMILE in Luxembourg.
If you have any request (feature, support, ...): create an issue on github.
If you want to get in touch with author: --NOSPAM-- phil ..AT.. P1sec ..DOT.. com --THANKS--

