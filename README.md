# python_parameters
# Using a parameters in a class (Python)
## At the beginning you need to move to the to the source file in the ros2 direction
## create a new file 
```
ros2 pkg create --build-type ament_python python_parameters --dependencies rclpy
```
< the output will be >
```
going to create a new package
package name: python_parameters
destination directory: /home/beka/ros2_foxy/src
package format: 3
version: 0.0.0
description: TODO: Package description
maintainer: ['beka <bedboy383@gmail.com>']
licenses: ['TODO: License declaration']
build type: ament_python
dependencies: ['rclpy']
creating folder ./python_parameters
creating ./python_parameters/package.xml
creating source folder
creating folder ./python_parameters/python_parameters
creating ./python_parameters/setup.py
creating ./python_parameters/setup.cfg
creating folder ./python_parameters/resource
creating ./python_parameters/resource/python_parameters
creating ./python_parameters/python_parameters/__init__.py
creating folder ./python_parameters/test
creating ./python_parameters/test/test_copyright.py
creating ./python_parameters/test/test_flake8.py
creating ./python_parameters/test/test_pep257.py

[WARNING]: Unknown license 'TODO: License declaration'.  This has been set in the package.xml, but no LICENSE file has been created.
It is recommended to use one of the ament license identitifers:
Apache-2.0
BSL-1.0
BSD-2.0
BSD-2-Clause
BSD-3-Clause
GPL-3.0-only
LGPL-3.0-only
MIT
MIT-0
```
<< At the parameters file you need to create a new file by using a "touch" function >>
```
touch python_parameters_node.py
```
## After creating a new file u need to add code as shown at the example.
```
colcon build --packages-select python_parameters
```
<< with the output in this setuation you will see the main output >>

```
Starting >>> python_parameters
--- stderr: python_parameters                   
/usr/lib/python3/dist-packages/setuptools/command/install.py:34: SetuptoolsDeprecationWarning: setup.py install is deprecated. Use build and pip and other standards-based tools.
  warnings.warn(
---
Finished <<< python_parameters [0.75s]

Summary: 1 package finished [0.91s]
  1 package had stderr output: python_parameters
```
## By openning a new terminal you will see a main output
```
. install/setup.bash
ros2 run python_parameters param_talker
```
## now you can see the specific output

```
[INFO] [1664882739.987161169] [minimal_param_node]: Hello world!
[INFO] [1664882741.980220512] [minimal_param_node]: Hello world!
[INFO] [1664882743.981279428] [minimal_param_node]: Hello world!
[INFO] [1664882745.980066608] [minimal_param_node]: Hello world!
[INFO] [1664882747.980920497] [minimal_param_node]: Hello world!
[INFO] [1664882749.981137762] [minimal_param_node]: Hello world!
[INFO] [1664882751.980063621] [minimal_param_node]: Hello world!
...
```

## In the new terminal
```
ros2 param list
```
```
/minimal_param_node:
  my_parameter
  use_sim_time
```
```
ros2 param set /minimal_param_node my_parameter earth
```
```
Set parameter successful
```
