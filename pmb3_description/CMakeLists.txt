cmake_minimum_required(VERSION 2.8.3)
project(pmb3_description)

find_package(catkin REQUIRED)

catkin_package()

foreach(dir gazebo  meshes robots urdf config)
    install(DIRECTORY ${dir}/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)

#############
## Testing ##
#############

if(CATKIN_ENABLE_TESTING)
    find_package(rostest REQUIRED)
    add_rostest(test/test_pmb3.test)
endif()
