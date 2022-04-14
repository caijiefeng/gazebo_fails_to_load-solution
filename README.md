# gazebo_fails_to_load-solution
Gazebo sometimes has a black screen or freezes problem,here is a solution.
## solution
### firstly you should create a workspace 
```
mkdir -p ~/my_ws/src
cd my_ws/src
catkin_init_workspace
cd ..
catkin_make # catkin build is also allowed
```
### make sure the git and the libgazebo-dev was already installed
if not
```
sudo apt-get install git
sudo apt-get install -y libgazebo11-dev
```
### source the gazebo_ros_pkgs
Pull the source code of gazebo_ros_pkgs from the github repository.
```
cd my_ws/src
git clone https://github.com/ros-simulation/gazebo_ros_pkgs.git -b noetic-devel
```
Use rosdep to install all the dependences
```
rosdep install --from-paths . --ignore-src
```
Then catkin build.
```
catkin build
```
Remeber to source or this solution will not work.
```
echo "source ~/my_ws/devel/setup.bash" >> ~/.bashrc
```
After doing this work,you can enjoy your gazebo!
