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
