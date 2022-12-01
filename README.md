RT1-assignment1

 Università di Genova
MSc in Robotics Engineering
Research Track 1
Presented by: Behnam Jabbari kalkhroan

**Introduction**
============================
This project includes the #Python script  for the assignment1, together with the Python Robotics Simulator based on a student Project
The  script is available on the directory  ```shell \robot-sim\assignment.py```
the file can be launched by this line:
```shell
$ python2 run.py assignment.py
```

**Running the program**
============================
The simulator requires a Python 2.7 installation, the [pygame](http://pygame.org/) library, [PyPyBox2D](https://pypi.python.org/pypi/pypybox2d/2.1-r331), and [PyYAML](https://pypi.python.org/pypi/PyYAML/).

to install the so called libraries you can use the belowed usefull codes

```shell
$ pip install virtualenv
$ git clone https://github.com/amanarora9848/unige-rt1-assignment1.git
$ cd unige-rt1-assignment1
$ virtualenv -p /usr/bin/python2.7 .rt1project1
$ . .rt1project1/bin/activate
```
## The Exercise
-----------------------------

To run the scripts in the simulator, use `run.py`, passing to it the file names.

```shell
$ python run.py assigment.py
```

Robot  application programming interface (API)
---------

The API for  a simulated robot is designed to be as similar  to the https://studentrobotics.org/docs/programming/sr/.

