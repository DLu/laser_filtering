cmake_minimum_required(VERSION 3.10.2)
project(map_laser)

find_package(catkin REQUIRED COMPONENTS nav_msgs rospy sensor_msgs std_msgs tf)

catkin_package(
    CATKIN_DEPENDS nav_msgs rospy sensor_msgs std_msgs tf
)

if(CATKIN_ENABLE_TESTING)
  find_package(catkin REQUIRED COMPONENTS roslaunch roslint)
  roslaunch_add_file_check(lfilter.launch)
  roslint_python()
  roslint_add_test()
endif()

install(FILES filters.yaml lfilter.launch
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

catkin_install_python(PROGRAMS scripts/filter.py
                      DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
