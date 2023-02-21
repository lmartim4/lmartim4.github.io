# Como usar o UUV_Sim

Simulador de ROV para gazebo e ROS

[Unmanned Underwater Vehicle Simulator Documentation](https://uuvsimulator.github.io/)

> Com o simulador instalado, é preciso usar `source $HOME/catkin_ws/devel/setup.bash` para configurar esse ambiente de trabalho
> 

<aside>
💡 `Dica: adicionar esse comando ao fim do .bashrc pode facilitar sua vida`

</aside>

<aside>
⚙ Rode “roslaunch uuv_gazebo_worlds auv_underwater_world.launch” para testar se o simulador foi instalado corretamente.

</aside>

## Criar um novo veículo

[Create new vehicle - Unmanned Underwater Vehicle Simulator Documentation](https://uuvsimulator.github.io/packages/uuv_simulator/docs/tutorials/create_new_vehicle/)

### rosrun uuv_assistants create_new_robot_model --robot_name mandi2

```bash
the rosdep view is empty: call 'sudo rosdep init' and 'rosdep update'
Create new catkin package for a UUV robot description
        Robot name = mandi2
        Catkin package name = mandi2_description
Creating the catkin package...
Created file mandi2_description/package.xml
Created file mandi2_description/CMakeLists.txt
Successfully created files in /home/lmartim4/catkin_ws/mandi2_description. Please adjust the values in package.xml.
Done!
Creating folder=mandi2_description/robots
Creating file:
        mandi2_description/robots/default.xacro
Creating folder=mandi2_description/urdf
Creating file:
        mandi2_description/urdf/gazebo.xacro
Creating file:
        mandi2_description/urdf/sensors.xacro
Creating file:
        mandi2_description/urdf/base.xacro
Creating file:
        mandi2_description/urdf/snippets.xacro
Creating file:
        mandi2_description/urdf/actuators.xacro
Creating folder=mandi2_description/meshes
Creating file:
        mandi2_description/meshes/README.md
Creating folder=mandi2_description/launch
Creating file:
        mandi2_description/launch/upload.launch
Robot description package <mandi2_description> create successfully
```

<aside>
📖 Foi reaproveitado o CAD (vehicle.dae) e o STL (vehicle.stl) da sophia

</aside>