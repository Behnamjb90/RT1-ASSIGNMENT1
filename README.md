**RT1-assignment1**

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
$ git clone https://github.com/Behnamjb90/RT1-ASSIGNMENT1
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

approach
-------
the Robot class given by the Professor. 
Here are presented:

### DC motors

The simulated robot has two motors and is connected to a two-output:
The left motor is connected to output `0` and the right motor to output `1`.

The Motor Board API is identical to [that of the SR API](https://studentrobotics.org/docs/programming/sr/motors/), except that motor boards cannot be addressed by serial number. So, to turn on the spot at one quarter of full power, one might write the following:

```python
R.motors[0].m0.power = 25
R.motors[0].m1.power = -25
```

### The Grabber

The robot is equipped with a grabber, which picks up a token which is attached to the front side of the robot and within 0.4 metres of the robot's centre. To pick up a token, we should call the `R.grab` method:

```python
success = R.grab()
```

The `R.grab` function answers `True` if a token was successfully called, or `False` otherwise. in the case that the robot is already holding a token, it will throw an `AlreadyHoldingSomethingException`.

To drop the token, we call the `R.release` method.
### Vision 

To help the robot find tokens and navigate, each token has markers stuck to it, as does each wall. The `R.see` method returns a list of all the markers the robot can see, as `Marker` objects. The robot can only see markers which it is facing towards.

Each `Marker` object has the following attributes:

* `info`: a `MarkerInfo` object describing the marker itself. Has the following attributes:
  * `code`: the numeric code of the marker.
  * `marker_type`: the type of object the marker is attached to (either `MARKER_TOKEN_GOLD`, `MARKER_TOKEN_SILVER` or `MARKER_ARENA`).
  * `offset`: offset of the numeric code of the marker from the lowest numbered marker of its type. For example, token number 3 has the code 43, but offset 3.
  * `size`: the size that the marker would be in the real game, for compatibility with the SR API.
* `centre`: the location of the marker in polar coordinates, as a `PolarCoord` object. Has the following attributes:
  * `length`: the distance from the centre of the robot to the object (in metres).
  * `rot_y`: rotation about the Y axis in degrees.
* `dist`: an alias for `centre.length`
* `res`: the value of the `res` parameter of `R.see`, for compatibility with the SR API.
* `rot_y`: an alias for `centre.rot_y`
* `timestamp`: the time at which the marker was seen (when `R.see` was called).

For example, the following code lists all of the markers the robot can see:

```python
markers = R.see()
print "I can see", len(markers), "markers:"

for m in markers:
    if m.info.marker_type in (MARKER_TOKEN_GOLD, MARKER_TOKEN_SILVER):
        print " - Token {0} is {1} metres away".format( m.info.offset, m.dist )
    elif m.info.marker_type == MARKER_ARENA:
        print " - Arena marker {0} is {1} metres away".format( m.info.offset, m.dist )
```

[sr-api]: https://studentrobotics.org/docs/programming/sr/

Conclusions
-----------
This project was very nice since i practiced a lot python coding. Furthermore I learned a lot about github, a platform that was so dark for me but after entering to this environment I understood more about that and I would like to involve more and practice.

