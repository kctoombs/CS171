To run PRM: ./paxos [siteID] setup.txt
Where siteID is the ID assigned to this site.
After hitting enter, all sites open up connections to each other. This takes some time (about 20 seconds).
Once these connections are made, the terminal will alert the user that the PRM is ready to receive commands.
Run all of the PRM executables first. Make sure to run the CLI executables only after all of the PRMs have connected to each other. The CLIs listen on a port number that is 3 greater than the port number of its corresponding PRM. 
To run CLI: ./cli [myPort] [prmPort]
Where myPort is the port that the CLI is listening on, and prmPort is the port that this CLI's corresponding PRM is listening on.
5/23/17, 4:33 PM:
A sample run looks like this:
./paxos 1 setup.txt (listening on port 5001)
./paxos 2 setup.txt (listening on port 5002)
./paxos 3 setup.txt (listening on port 5003)
All paxos processes connect to each other (~20 seconds)
./cli 5004 5001
./cli 5005 5002
./cli 5006 5003
All CLIs connect to their PRMs (~10 seconds)

Order of execution: Start PRMs, then Mappers, then reducer, then CLI

5/31/17, 5:31 PM:
A sample run looks like this (for one node):
./paxos 1 setup.txt&
./mapper 5007 5004 1&  (listening on port 5007, id of mapper is 1)
./reducer 5010 5004&  (listening on port 5010)
./cli 5004 5001 5007 5010  (listening on port 5004, prm is 5001, 5007 is mapper, 5010 is reducer)
