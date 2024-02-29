# ros2_setup

--symlink-install doesn't work - are you kidding me?
https://github.com/colcon/colcon-core/pull/592


Example for multiple projects


```
PROJECT=ROBOFORGE

## LEANIS
if [ "$PROJECT" = LEANIS ]; then
    source /opt/ros/melodic/setup.bash
    LEANIS_WS=${HOME}/leanis_ws
    #LEANIS_WS=${HOME}/leanis_heave_ws
    source ${LEANIS_WS}/devel/setup.bash
    #source ${HOME}/moveit_ws/devel/setup.bash
    export PATH=$PATH:${LEANIS_WS}/src/ardupilot/Tools/autotest
    export PATH=/usr/lib/ccache:$PATH
    # For docker, you will also need
    export PATH=${HOME}/.local/bin:$PATH
elif [ "$PROJECT" = DAVE ]; then
    # DAVE
    source /opt/ros/noetic/setup.bash
    source ${HOME}/uuv_ws/devel/setup.bash
elif [ "$PROJECT" = ME4823 ]; then
    ## ME4823
    source /opt/ros/noetic/setup.bash
    source ${HOME}/me4823_ws/devel/setup.bash
elif [ "$PROJECT" = ABV ]; then
    # ROS Setup
    source /opt/ros/noetic/setup.bash
    export ABV_WS="${HOME}/Projects/MOE/ABV3/abv_ws"
    source ${ABV_WS}/devel/setup.bash
    # FVS/AVS Setup
    export FVS_ROOT="${ABV_WS}/src/fvs"
    export FVS_ROOT_DIR="${FVS_ROOT}/trunk"
    export AVS_ROOT_DIR="${ABV_WS}/src/avs"
    alias cdAvs="cd ${AVS_ROOT_DIR}"
    alias cdFvs="cd ${FVS_ROOT_DIR}"

elif [ "$PROJECT" = GFOE ]; then
    export DEVWD=${HOME}/gfoe_ws/src
    source /opt/ros/melodic/setup.bash
    source ${HOME}/gfoe_ws/devel/setup.bash
elif [ "$PROJECT" = SANDWICH ]; then
    source /opt/ros/noetic/setup.bash
    source ${HOME}/sandwich_ws/devel_isolated/setup.bash
elif [ "$PROJECT" = VRX ]; then
    ## ME4823
    source /opt/ros/noetic/setup.bash
    source ${HOME}/vrx_ws/devel/setup.bash
elif [ "$PROJECT" = MBZIRC ]; then
    source /opt/ros/galactic/setup.bash
    source ${HOME}/mbzirc_ws/install/setup.bash
elif [ "$PROJECT" = VRX2 ]; then
    source /opt/ros/galactic/setup.bash
    source ${HOME}/vrx2_ws/install/setup.bash
elif [ "$PROJECT" = STONEFISH ]; then
    ## ME4823
    source /opt/ros/noetic/setup.bash
    source ${HOME}/stonefish_ws/devel/setup.bash
elif [ "$PROJECT" = ROBOFORGE ]; then
    ## ROS2 Setup
    source /opt/ros/humble/setup.bash
    export ROS_LOCALHOST_ONLY=1
    # Colcon setup
    source /usr/share/colcon_cd/function/colcon_cd.sh
    export _colcon_cd_root=/opt/ros/humble/
    # Local workspace setup
    source ${HOME}/tb4_ws/install/local_setup.bash
else
    echo "WARNING: No PROJECT specified in .bashrc"
fi
```
