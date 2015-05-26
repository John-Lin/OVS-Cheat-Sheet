# OVS-Cheat-Sheet
Open vSwitch Cheat Sheet

An overview of Openvswitch implementation

```
                                                                                       
 +---------+ +-----------+                                                              
 |ovs-ofctl| |sFlow Trend|                                                                         
 +----^----+ +-----^-----+                                                                         
      |            |                                                                      Remote   
+----------------------------------------------------------------------------------------------+   
      |            |                                                                               
      |      sFlow |                                                                               
      |            |  +---------+   +----------+             +---------+   +------------+          
      |            |  |ovs-dpctl|   |ovs-appctl|             |ovs-vsctl|   |ovsdb-client|          
      |            |  +----+----+   +------^---+             +-----+---+   +-------^----+          
      |            |       |     Command   |                       | Config        | DB operation  
      |            |  +----v---------------v--+ Unix socket   +----v---------------v-+             
      |            +--+                       +--------------->                      | 
      |OpenFlow       |    ovsdb-vswitchd     |               |     ovsdb-server     | +----------+
      +---------------+                       <---------------+                      | |ovsdb-tool|
                      +-----^------------+----+ Apply changes +------------^---------+ +----+-----+
                            |            |                                 |                |      
                            |            |                                 |                |      
                            |            |                           +-----v-----+          |      
             upcall(netlink)|            |netlink                    |   ovsdb   <----------+      
                            |            |                           +-----------+                 
+----------------------------------------------------------------------------------------------+   
                            |            |                                       Kernel space      
                      +-----+------------v------+                                                  
                      |                         |                                                  
                      |Openvswitch kernel module|                                                  
                      |                         |                                                  
                      +-------------------------+                                                  
```




## ovs-vsctl

```
ovs-vsctl –V
```

```
ovs-vsctl show
```

```
ovs-vsctl list-br
```

```
ovs-vsctl list-ports <bridge>
```

```
ovs-vsctl add-br <bridge>
```

```
ovs-vsctl add-port <bridge> <interface>
```

```
ovs-vsctl set-controller <bridge> tcp:<IP>:<port>
```

```
ovs-vsctl get-controller <bridge>
```

```
ovs-vsctl del-controller <bridge>
```


## ovs-ofctl

## ovs-dpctl

## ovs−appctl
