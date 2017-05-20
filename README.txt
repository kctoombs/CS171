To run: ./paxos [siteID] setup.txt
Where siteID is the ID assigned to this site.
After hitting enter, all sites open up connections to each other. This takes some time (about 20 seconds).
Once these connections are made, the terminal will alert the user that the PRM is ready to receive commands.
Run all of the PRM executables first. Make sure to run the CLI executables only after all of the PRMs have connected to each other. The CLIs listen on a port number that is 3 greater than the port number of its corresponding PRM. 
