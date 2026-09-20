# CS 123: Forward Kinematics Lab

Student code for the forward kinematics lab. You will implement the forward kinematics of
Pupper's front-left leg (`leg_front_l_1`, `leg_front_l_2`, `leg_front_l_3`) and visualize the
end-effector position in RViz2.

## Files

- `forward_kinematics.py` — ROS 2 node that subscribes to `/joint_states` and publishes the
  end-effector position on `leg_front_l_end_effector_position` and a sphere on `marker`.
  Fill in `rotation_y`, `rotation_z`, `translation`, and the transforms `T_1_2`, `T_2_3`,
  `T_3_ee`, `T_0_ee`, and `end_effector_position`. `rotation_x` and `T_0_1` are given.
- `forward_kinematics.launch.py` — launches `ros2_control_node`, the robot state publisher,
  the joint state / IMU broadcasters, the kp/kd forward command controllers, and the
  Foxglove bridge.
- `forward_kinematics.yaml` — controller configuration (update rate, joints, broadcasters).
- `forward_kinematics.rviz` — RViz2 config with the robot model and the end-effector marker
  already added.
- `forward_kinematics_layout.json` — Foxglove layout, if you prefer Foxglove to RViz2.

The node holds the legs limp by continuously commanding zero kp and kd, so you can move the
leg by hand and watch the marker follow it.

## Running

```bash
ros2 launch forward_kinematics.launch.py   # in one terminal
python3 forward_kinematics.py              # in another
rviz2 -d forward_kinematics.rviz           # in a third
```
