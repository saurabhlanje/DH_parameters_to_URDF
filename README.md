# How to quickly generate URDF file from the DH parameters #
DH parameters are extensively used in robotics research for defining the configuration of joints in the serial link robotic arms. When ROS is being used for the simulation of robotic arm with defined DH parameters it becomes necessary to make a URDF file of the robotic arm which represents the configuration of joints similar to the DH parameters. To ease this activity a small macro is made in URDF XML file which can quickly generate the URDF file based on the DH parameter provided. Currently the macro only supports revolute joint. Similar effort is made in this contribution [here](https://github.com/AdoHaha/DH2URDF) and [here](https://adohaha.github.io/DH2URDF/) as well.
But in this work, a simplified shape of link is also added which is just for the representation purpose. Along with DH parameter, other features like the colour and link diameter, joint limits can also be defined.

## Steps to make a URDF ##
1. Initially a world link is created for reference
2. Using macro (XACRO) definitions of link connected to world link is added and then followed by link connected to the first link and so on
3. Format to add link to existing link is as follows
```
<xacro:DH_link link_no="0"
a="0" 
alpha="1.57"
d="0.0"
link_dia=".05"
colour_r="1"
colour_g="0"
colour_b="0"
colour_a="0.5"
parent_link_name="world"
mass="1"
limit_min="3.14"
limit_max="-3.14"
vel_max="10"
effort_max="10" />
```
4. The name of the parent link must be world link for the first link only afterwards the name of parent link should be ```Link_0_child_frame``` which tells that the link 1 is connected to child link for the link 0. Similarly parent names are to be provided.
5. For quick reference, the DH parameters for UR5 and PUMA 560 robotic arm is provided.


