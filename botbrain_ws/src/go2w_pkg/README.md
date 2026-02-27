# go2_pkg

The Go2 robot-specific package for the R1 robot platform. This package provides all the necessary components, configurations, and interfaces specifically designed for the Unitree Go2 quadruped robot.

## Description

The `go2_pkg` package serves as the robot-specific implementation for the Unitree Go2 quadruped robot platform. It contains all the hardware-specific configurations, service definitions, robot description files, and control interfaces required to operate the Go2 robot within the R1 robot system.

## Directory Structure

```
go2_pkg/
├── action/                      # ROS2 action definitions
├── config/                      # Configuration files
│   ├── nav2_params.yaml        # Nav2 navigation parameters
│   ├── nav2_params_new.yaml    # Updated Nav2 parameters
│   ├── nav2_params_old.yaml    # Legacy Nav2 parameters
│   └── pointcloud_to_laserscan_params.yaml  # Point cloud to laser scan conversion
├── go2_pkg/                     # Python package
│   └── __init__.py             # Package initialization
├── go2_setup.bash              # Go2-specific environment setup script
├── include/                     # C++ header files
│   └── go2_pkg/                # C++ header directory
├── launch/                      # Launch files
│   ├── pc2ls.launch.py         # Point cloud to laser scan launcher
│   └── robot_interface.launch.py  # Main Go2 robot interface launcher
├── meshes/                      # 3D mesh files for robot visualization
│   ├── calf.dae                # Calf mesh (Collada format)
│   ├── calf_mirror.dae         # Mirrored calf mesh
│   ├── foot.dae                # Foot mesh
│   ├── go2_interface.stl       # Go2 interface mesh (STL format)
│   ├── hip.dae                 # Hip mesh
│   ├── thigh.dae               # Thigh mesh
│   ├── thigh_mirror.dae        # Mirrored thigh mesh
│   └── trunk.dae               # Main body trunk mesh
├── scripts/                     # Executable Python scripts
│   ├── go2_controller_commands.py  # Go2 control command handler
│   ├── go2_read.py             # Go2 sensor data reader
│   ├── go2_video_stream.py     # Go2 video stream handler
│   └── go2_write.py            # Go2 command writer
├── src/                         # C++ source files
├── srv/                         # ROS2 service definitions
│   ├── BodyHeight.srv          # Body height control service
│   ├── ContinuousGait.srv      # Continuous gait control service
│   ├── CurrentMode.srv         # Current mode query service
│   ├── Euler.srv               # Euler angle control service
│   ├── FootRaiseHeight.srv     # Foot raise height control service
│   ├── LightControl.srv        # Light control service
│   ├── Mode.srv                # Robot mode control service
│   ├── MoveForward.srv         # Forward movement service
│   ├── ObstacleAvoidance.srv   # Obstacle avoidance service
│   ├── Pose.srv                # Pose control service
│   ├── SpeedLevel.srv          # Speed level control service
│   ├── SwitchGait.srv          # Gait switching service
│   ├── SwitchJoystick.srv      # Joystick control service
│   └── Turn.srv                # Turning control service
├── urdf/                        # URDF robot description files
│   └── go2_description.urdf    # Go2 robot description in URDF format
├── xacro/                       # XACRO robot description files
│   ├── const.xacro             # Constants and parameters
│   ├── leg.xacro               # Leg definition macros
│   ├── materials.xacro         # Material definitions
│   └── robot.xacro             # Main robot description
├── CMakeLists.txt              # CMake build configuration
└── package.xml                 # Package manifest
```

## Folder Explanations

### `action/`
Contains ROS2 action interfaces for complex robot behaviors that require feedback and can be cancelled. Actions are used for long-running tasks like navigation goals or complex movements.

### `config/`
Stores configuration files specific to the Go2 robot:
- **Nav2 Parameters**: Navigation stack configuration files with robot-specific settings
- **Point Cloud Processing**: Parameters for converting point cloud data to laser scan format
- **Robot-Specific Settings**: Hardware-specific configurations and tuning parameters

### `go2_pkg/`
Python package directory containing Python modules and utilities specific to the Go2 robot implementation.

### `go2_setup.bash`
Environment setup script that configures:
- ROS2 environment variables
- Network configuration for Go2 communication
- Robot-specific IP settings and network interfaces

### `include/`
C++ header files directory for any C++ implementations or libraries specific to the Go2 robot.

### `launch/`
ROS2 launch files for starting Go2-specific nodes and services:
- **Robot Interface**: Main launcher for all Go2 robot nodes and services
- **Point Cloud Processing**: Launcher for point cloud to laser scan conversion

### `meshes/`
3D mesh files for robot visualization and simulation:
- **Collada (.dae)**: High-quality mesh files for detailed robot visualization
- **STL (.stl)**: Standard mesh format for 3D printing and basic visualization
- **Robot Components**: Individual mesh files for each robot part (legs, body, feet)

### `scripts/`
Executable Python scripts for Go2 robot control:
- **Controller Commands**: Handles high-level robot control commands
- **Data Reading**: Reads sensor data and robot state information
- **Video Streaming**: Manages camera and video stream functionality
- **Command Writing**: Sends commands to the robot hardware

### `src/`
C++ source files directory for any C++ implementations specific to the Go2 robot.

### `srv/`
ROS2 service definitions for Go2 robot control:
- **Movement Services**: Forward movement, turning, and pose control
- **Mode Services**: Robot mode switching and status queries
- **Hardware Services**: Light control, gait switching, and obstacle avoidance
- **Configuration Services**: Body height, foot raise height, and speed control

### `urdf/`
URDF (Unified Robot Description Format) files that define the Go2 robot's physical structure, joints, and links for simulation and visualization.

### `xacro/`
XACRO (XML Macros) files that provide a more flexible way to define robot descriptions:
- **Modular Design**: Separate files for different robot components
- **Parameterization**: Configurable parameters and constants
- **Reusability**: Macro definitions for repeated components like legs

## Contributing

1. **Create Feature Branch**: Create a new branch from `dev` named `feature/[name_of_feature]`
2. **Development**: Make your changes following Go2-specific patterns
3. **Testing**: Test with actual Go2 robot hardware
4. **Documentation**: Update this README with any new features or changes
5. **Submit Pull Request**: Create a pull request to the `dev` branch

---

**Note**: This package is specifically designed for the Unitree Go2 robot. Ensure proper hardware connection and Go2 SDK installation before use.
# go2w_pkg
