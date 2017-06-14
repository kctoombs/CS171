To run PRM: ./paxos [siteID] setup.txt
Where siteID is the ID assigned to this site.
After hitting enter, all sites open up connections to each other. This takes some time (about 15 seconds).
Once these connections are made, the terminal will alert the user that the PRMs are connected. At this point, run the mappers, the reducer, and the CLI.

There is a 12 second timeout for every CLI command. Each time the CLI sends a command, something should print, so make sure to wait for something to print before running another command. The CLI will also alert you if the command timed out.
 
Order of execution: Start PRMs, then Mappers, then reducer, then CLI

6/12/17, 12:31 AM:
A sample run looks like this (for one node):
./paxos 1 setup.txt &
./mapper 1 &  (id of mapper is 1)
./mapper 2 &  (id of mapper is 2)
./reducer &  
./cli 
