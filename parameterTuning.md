# Localization: Parameter Tuning

## Part I

1. get rid of the transform timeout error by tuning the transform_tolerance parameter in both amcl node in amcl.launch and move_base node in costmap_common_params.yaml. a key to indicate success is once this parameter is tuned properly, all three maps can be visualized inside Rviz and no errors should be printed in terminal
2. map update loop. check the info in terminal, it says it actually took 0.039 seconds. That means 25 Hz instead of 50. change both update_frequency and publish_frequency to 25 Hz

## Part II

Tune the cost map parameters

First fill in the default values from ROS wiki.

The robot navigates, but will drop off path frequently, seems like it was trying too hard to avoid the obstacles.

Turns out the flickering has nothing to do with the transform_tolerance, the default value of 0.1 will do just fine. The problem is in Rviz, if you choose Interact on the tools menubar, the screen WILL flicker. Choose another tool, i.e. "move camera" the flickering disappears

tweak costmap parameters
obstacle_range: 2.5
raytrace_range: 2.0
inflation_radius: 0.3
test run 1.gif

obstacle_range: 2.0
raytrace_range: 2.5
inflation_radius: 0.3
test run 2.gif
