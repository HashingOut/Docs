Project 1

Findings & Documentation

<b>Research question</b>

How do I setup a personal IRC server
on Ubuntu Linux?

There are multiple methods of creating and using this type of
server. Most of the results I found online walked you through installation,
either from source or via package manager. I could not find a single server
program that could be easily installed via a GUI interface. All operations had
to be performed in a command line. �

## Process

I started by viewing the instructions from [https://www.unrealircd.org/docs/Installing_from_source](https://www.unrealircd.org/docs/Installing_from_source).

These steps show how to install UnrealIRCD
from source via the apt or yum command suite. To start,

<b>Download</b>

I needed to download the tar file
and the instructions gave a specific command for this. However, since I had run
into issues with using old repositories, I decided to find the link on their
site to download the source file via the browser. I then extracted the file
with �tar xzvf� and changed the directory to the new
folder since the downloads was not the original intended location for this file.

�<b>Install</b>

Inside the unrealircd-X.X.X
folder (X donating version number), I ran the configuration program with �./Config�. This gave multiple prompts asking for various
settings. I chose all the defaults. I then had to use the �make� command inside
this directory. However, this command suite was not installed. I used the �apt�
suit to find and install this for Ubuntu. I was then able to successfully use
the �make� and then �make install� commands to finalize the installation.�

<b>Configuration</b>

Next, I had to move the
configuration file from the unrealircd directory to
my machine�s main configuration directory using a simple copy command. After
this, I can use a text editor to view and edit the .conf file. A number of changes MUST be made prior to
being able to start the server, and the UnrealIRCd
website has a great [outline of the configuration setup](https://www.unrealircd.org/docs/Configuration).�

<b>Starting</b>

Issuing the command �./unrealircd start� will begin the server, but I did run into
a few errors. A few of the configuration settings were not valid. Also, SSL
needed to be installed. This again was a process of using the apt commands to
install this protocol for the server.

<b>Running</b>

Once the server is running, I
needed to setup the server on my IRC client. This was a big step that the UnrealIRCd site did NOT specify. Additionally, Pidgin did
not provide (to my knowledge) the ability to create a new server. The GUI for
this application was too simple with inadequate amounts of options and
settings. Ended up downloading ******. This client allowed me to customize my
servers.

I then created a new server (titled ETR 149) out of the list of
available servers using my server�s IP info. Had someone try to connect into
the chat room. In my case, users needed to be connected to the same network as
me (there being several to choose from at the school.)

Success!

## Requirements

<b>Hardware</b>

Any typical, modern desktop computer should be plenty. I used
a Dell Optiplex workstation with an FX4500 processer
from AMD and a small SSD in storage. �

<b>Software</b>

Multiple bits and pieces are needed to create an IRC server.
Once the server software is installed and setup, it will list any errors after
you tell it to start. �

<b>Network</b>

There should be no issues with connectivity when running this
service within your own network. Having clients connect from outside the
network was a part I did not try.

I recommend a cabled connection. But realistically, it�s a
simple chat server; you won�t be streaming videos in 4k with this thing. My
setup was on the WiFi using an ancient USB network
adapter.

## Risks

At first, I needed to consider the security risks in setting
up this type of open server. However, since the server was running inside a
network with no probable outside connection, security was less of a concern.
Besides, none of the hardware or software was mine��
