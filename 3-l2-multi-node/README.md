# Single L2 Network

An example of creating a single L2 network of 2 nodes, each containing 
2 networks namespaces (containers), connected via a bridge.

Create the 2 VMs (container-networking-1 and container-networking-2):

```
vagrant up
```

SSH to each node (VM) in turn, and run the setup script to create the network namespaces connected via bridge: 

```
vagrant ssh container-networking-[12]
cd /vagrant
./setup.sh
```

To see the status of the interfaces/route tables within each of the nodes and the namespaces, run:

```
./status.sh
```

To test the connectivity between the containers within and node, and across nodes, run the following:

```
./test.sh
```