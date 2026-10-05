# URDF文件概述

- 统一机器人描述格式 (Unified Robot Description Format, URDF)
    - 本质：xml格式
    - <>

- link: name
    - inertial
        - origin: xyz,rpy
        - mass: value
        - inertia: ixx, ixy, ixz, iyy, iyz, izz
    - visual
        - origin: xyz,rpy
        - geometry
            - mesh: filename
        - material: name   % 在开头单独定义
    - collision
        - origin: xyz,rpy
        - geometry
            - mesh: filename


- joint: name, type ("revolute"/"fixed"/"floating")
    - origin: xyz, rpy  % 关节坐标系相对于父连杆的位姿（可写为齐次变换）
    - parent: link
    - child: link  % 子连杆一般与该关节的名称相同
    - axis: xyz  % 所绕的转轴（相对于关节坐标系）
    - limit: lower, upper, effort, velocity
    - 