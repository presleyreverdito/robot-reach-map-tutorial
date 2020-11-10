<h1>Reuleaux: how to visualize the reachability map with the robot</h1>

1- First you should clone the Kuka experimental repository:
	
	git clone https://github.com/ros-industrial/kuka_experimental.git
	
2- Run this follow command to install every depencies of Kuka repository:
	
	rosdep install -r -y --from-paths src --ignore-src

3- Now you can build the catkin workspace:

	catkin_make
	
4- Let's go what we want! First of all, in a terminal write:
	
	roslaunch kuka_<press tab 2 times>
	
you can see the options? If yes, you should choose the option of the robot that you have created the reachability map (If you don't have create your reachability map, pause this tutorial and go to [Reuleaux tutorial](http://wiki.ros.org/reuleaux))

In case of this tutorial we choose kr6 model, then:

	roslaunch kuka_kr6_support test_kr6r700sixx.launch
	
We use test_kr6r700sixx.launch file, but there are others launch file that you can test, feel free!
Afte you ran that command above, your computer should open rviz.

<img src="https://github.com/presleyreverdito/tutorial-images/blob/main/Screenshot%20from%202020-11-09%2017-21-34.png"
     alt="Rviz opened with robot"
     style="float: left; margin-right: 10px;" />
	

4.1- Sometime some package couldn't installed, you sould pay attention what the terminal shows you up. In my time, the joint_state_publisher_gui had wasn't installed, then I ran:

	sudo apt install ros-kinetic-joint-state-publisher-gui
  
5 - Now we should load the reachability map, in other terminal run:

	rosrun map_creator load_reachability_map kr6r700sixx.h5
	
Ok, if you could got here, every is going well.

6- Lets configure the rviz now. On left menu, in bottom, you can find the "add" buttom, click on it.

<img src="https://github.com/presleyreverdito/tutorial-images/blob/main/Screenshot%20from%202020-11-09%2017-24-32.png"
     alt="Rviz opened with robot"
     style="float: left; margin-right: 10px;" />
     
In "workspace_visualization" you select "ReachabilityMap" and then "OK".
  
<img src="https://github.com/presleyreverdito/tutorial-images/blob/main/Screenshot%20from%202020-11-10%2008-35-22.png"
     alt="Rviz opened with robot"
     style="float: left; margin-right: 10px;" />
  
  
Back to the left menu, now we should cofigure the reachability map.
  
<img src="https://github.com/presleyreverdito/tutorial-images/blob/main/Screenshot%20from%202020-11-10%2008-40-43.png"
alt="Rviz opened with robot"
style="float: left; margin-right: 10px;" />

In topic, choose "/reachbility_map". Now you already have the reachability with robot, but it isn't photogenic. Let's do it more photogenic!
In the left menu yet, choose "1st_Half" in disect and in Shape Property, choose size equal 0,02.


<img src="https://github.com/presleyreverdito/tutorial-images/blob/main/Screenshot%20from%202020-11-10%2008-55-38.png"
alt="Rviz opened with robot"
style="float: left; margin-right: 10px;" />

Is the robot in wrong pose? Calm down, Do you remeber that window that open in the same time as rviz? There you can change the pose of robot.

<img src="https://github.com/presleyreverdito/tutorial-images/blob/main/Screenshot%20from%202020-11-10%2008-52-34.png"
alt="Rviz opened with robot"
style="float: left; margin-right: 10px;" />
 	
Have fun! Feel free to change the positions!

Thank you for read this tutorial, if you have any advise or tips, feel free to contact me! :)
