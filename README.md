# Advanced-Functional-System-Engineering

![Badge Status](https://ci-as-a-service)

##Overview

�ֵ��β���

## Description

�ֵ������ROS�ѥå������Ǥ�.

toyoarm_moveit_config�Ǥ�moveit�Ǽ���Υ������ư�����ޤ�.

diff_mobile_robot�Ǥϼ�������դ���ư��ܥåȤ�gazebo��ǥʥӥ�������󤷤ޤ�.

toyoarm�ˤ�8���������urdf������ޤ�.



## RUN

1.�������Υ�ǥ��moveit��ư����

$roslaunch toyoarm_moveit_config demo.launch

2.��������դ���ư��ܥåȤ�gazebo��ǥʥӥ�������󤹤�

- 1st terminal
���ߥ�졼����ư���ޤ�.
	$roslaunch diff_mobile_robot diff_mobile_gazebo.launch

- 2nd terminal

����˻����ͤ����äƥ������Ǥ�դλ����ˤ���.

	$roslaunch diff_mobile_robot toyoarm_control.launch

- 3nd terminal

��Ȥ���,����5���Ф���0.5[rad]ư�������ޥ�ɤ�¹Ԥ���.

	$rostopic pub -1 /toyoarm/joint5_position_controller/command std_msgs/Float64 "data: 0.5"

- 4th terminal

�ʥӥ��������򤹤�.

	$roslaunch diff_mobile_robot amcl.launch

- 5th terminal

��ư���λؼ���Ԥ�.

	$rosrun	rviz rviz
	
��ư��,amcl.launch�ˤ�ä�publish���줿/map��By topic����õ����ɽ��������.
���˲��̾����������:2D Nav Goal�򥯥�å�����map�Υ��������������Ȱ�ư��Ϥ��.