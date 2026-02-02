# create_description

A place for URDF models and meshes for iRobot's Create 1 and 2.

## Dimensions and Inertia

Roomba's dimensions are roughly known from [this source](https://socialcompare.com/en/review/irobot-roomba-625#:~:text=Table_title:%20iRobot%20Roomba%20625%20Table_content:%20header:%20%7C,Name:%20Website%20%7C%20iRobot%20Roomba%20625:%20%7C):

Height (total): 9 cm
Height (`base_link`): 0.0611632 m
Diameter: 34 cm
Mass: 3.5 kg

Roomba's inertia can be simplified to a [cylinder](https://en.wikipedia.org/wiki/List_of_moments_of_inertia#Moments_of_inertia):

```
Ixx = Iyy = 1/12 * Mass * (3*R^2 + H^2) = 0.024898546 kg*m^2
Izz = 1/2 * M * R^2 = 0.047614879 kg*m^2
```

Some other sensors (e.g. leftfront_cliff_sensor_link) are assigned some random very small values to satisfy [MuJoCo's constraints](https://github.com/google-deepmind/mujoco/issues/375#issuecomment-1179169053).

```
ixx + iyy >= izz
ixx + izz >= iyy
iyy + izz >= ixx
```

## Sources

* Original URDF and Create 1 mesh:  https://github.com/turtlebot/turtlebot_create
* Original Create 2 mesh:  https://github.com/goncabrita/roomba_robot
