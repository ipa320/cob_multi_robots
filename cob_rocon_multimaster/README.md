cob_rocon_multimaster
===============

General description
---------------------
This package contains configuration and launch files for enabling the use of multimaster setups based on the rocon_multimaster framework.

Testing Rocon communications
---------------------
PC 1: *roslaunch rocon_hub hub.launch*

PC 1: *roslaunch rocon_gateway gateway.launch gateway_firewall:=false*

PC 2: *roslaunch rocon_gateway gateway.launch gateway_firewall:=false*

PC 1: *rostopic pub -r 1 /test1 std_msgs/Int8 1*

PC 2: *rostopic pub -r 1 /test2 std_msgs/Int8 2*

PC 1: *rosrun rocon_gateway flip* -> *f* -> *0* -> *y*

PC 2: *rosrun rocon_gateway flip* -> *f* -> *0* -> *y*

PC 1: *rostopic echo /test2*

PC 2: *rostopic echo /test1*

Everything works as expected, if PC 1 receives "data: 2" and PC 2 receives "data: 1". For further information, execute *rosrun rocon_gateway gateway_info* and/or *rosrun rocon_gateway remote_gateway_info*.
