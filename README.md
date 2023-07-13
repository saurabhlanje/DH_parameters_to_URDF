# DH_parameters_to_URDF
DH parameters are extensively used in robotics research for defining the configuration of joints in the serial link robotic arms. When ROS is being used for the simulation of robotic arm with defined DH parameters it becomes necessary to make a URDF file of the robotic arm which represents the configuration of joints similar to the DH parameters. To ease this activity a small macro is made in URDF XML file which can quickly generate the URDF file based on the DH parameter provided. Currently the macro only supports revolute joint. Similar effort is made in this contribution [here](https://github.com/AdoHaha/DH2URDF) and [here](https://adohaha.github.io/DH2URDF/) as well.
But in this work, a simple shape of link is also added which is just for the representation purpose. Along with DH parameter, other features like the colour and link diameter, joint limits can also be defined.

Steps to make a URDF
Initially a world link is created for reference
