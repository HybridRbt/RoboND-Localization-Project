# Localization: Parameter Tuning

## Part I

1. get rid of the transform timeout error by tuning the transform_tolerance parameter in both amcl node in amcl.launch and move_base node in costmap_common_params.yaml. a key to indicate success is once this parameter is tuned properly, all three maps can be visualized inside Rviz and no errors should be printed in terminal
2. map update loop. check the info in terminal, it says it actually took 0.039 seconds. That means 25 Hz instead of 50. change both update_frequency and publish_frequency to 25 Hz

## Part II

Tune the cost map parameters

First fill in the default values from ROS wiki.
