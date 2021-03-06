#####  Simple Tree Topology with Fanout 2 (Professor: Nick Feamster)
source python code : https://d396qusza40orc.cloudfront.net/sdn/srcs/programming-assignment-2.zip
source assignment1 : http://www.cs.kent.edu/~mallouzi/Software%20Defined%20Networking/Assignment1.pdf

<j>Data center networks typically have a tree-like topology. End-hosts connect to top-of-rack switches, which form the leaves (edges) of the tree; one or more core switches form the root; and one or more layers of aggregation switches form the middle of the tree. In a basic tree topology, each switch (except the core switch) has a single parent switch. Additional switches
and links may be added to construct more complex tree topologies (e.g., fat tree) in an effort to improve fault tolerance or increase inter-rack bandwidth. In this assignment, your task is to create a simple tree topology. You will assume each level i.e., core, aggregation, edge and host to be composed of a single layer of switches/hosts with a configurable fanout value (k). For example, a simple tree network having a single layer per each level and a fanout of 2 looks like:</j>

<img src="https://github.com/syaifulahdan/mininet/blob/master/image/Screenshot%20from%202016-04-02%2002:44:01.png" align="center" title="syaifulahdan/mininet" />

download consists of two files:


- <a href="https://github.com/syaifulahdan/mininet/blob/master/py-custop_tree_topology_with_Fanout2-custom_topo.py">custom-topo.py:</a> a sekleton class which you will update with the logic for creating the datacenter topology described above.

- <a href="https://github.com/syaifulahdan/mininet/blob/master/py-custop_tree_topology_with_Fanout2-submit.py">submit.py:</a>  used to submit your code and output to the course servers for grading. You don’t have to do any modifications in here.

##### CustomTopo.py
The skeleton class takes following arguments as input:
- <b>linkopts1</b>: for specifying performance parameters for the links between core and aggregation switches.
- <b>linkopts2</b>: for specifying performance parameters for the links between aggregation and edge switches.
- <b>linkopts3</b>: for specifying performance parameters for the links between edge switches and host.
- <b>Fanout</b>: to specify fanout value i.e., number of childs per node.

Your logic should support setting at least bw and delay parameters for each link.

####Submitting your Code

To submit your code, run the submit.py script:
<pre>
$ sudo python submit.py
</pre>
Make sure that CustomTopo.py is in the same directory as submit.py. Your mininet VM should have internet access by default, but still verify that it has internet connectivity (i.e., eth0 set up as NAT). Otherwise submit.py will not be able to post your code and output to our course servers.
The submission script will ask for your login and password. This password is not the general account password, but an assignment-specific password that is uniquely generated for each student. You can get this from the assignments listing page.
Once finished, it will prompt the results on the terminal (either passed or failed). Note, if during the execution submit.py script crashes for some reason or you terminate it using CTRL+C, make sure to clean mininet environment using:
<pre>
$ sudo mn -c
</pre>

Also, if it still complains about the controller running. Execute the following command to kill it:
<pre>
$ sudo fuser -k 6633/tc
</pre>
