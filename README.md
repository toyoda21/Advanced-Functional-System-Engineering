# Advanced-Functional-System-Engineering

![Badge Status](https://ci-as-a-service)

##Overview

講義の課題

## Description

講義課題のROSパッケージです.

toyoarm_moveit_configではmoveitで自作のアームを動かします.

diff_mobile_robotでは自作アーム付き移動ロボットをgazebo上でナビゲーションします.

toyoarmには8軸アームのurdfがあります.



## RUN

1.自作アームのモデルをmoveitで動かす

$roslaunch toyoarm_moveit_config demo.launch

2.自作アーム付き移動ロボットをgazebo上でナビゲーションする

- 1st terminal
シミュレータを起動します.
	$roslaunch diff_mobile_robot diff_mobile_gazebo.launch

- 2nd terminal

関節に指令値を送ってアームを任意の姿勢にする.

	$roslaunch diff_mobile_robot toyoarm_control.launch

- 3nd terminal

例として,関節5に対して0.5[rad]動かすコマンドを実行する.

	$rostopic pub -1 /toyoarm/joint5_position_controller/command std_msgs/Float64 "data: 0.5"

- 4th terminal

ナビゲーションをする.

	$roslaunch diff_mobile_robot amcl.launch

- 5th terminal

移動場所の指示を行う.

	$rosrun	rviz rviz
	
起動後,amcl.launchによってpublishされた/mapをBy topicから探して表示させる.
次に画面上部の緑矢印:2D Nav Goalをクリックしてmapのゴール地点を決めると移動を始める.