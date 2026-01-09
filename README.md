# ROS2-URDF

This repository provides **URDF (Unified Robot Description Format)** implementations for **ROS 2** along with practical examples. It is designed to help beginners and intermediate users understand robot modeling concepts and structure their robots for simulation and visualization.

---

## What is URDF?

URDF (Unified Robot Description Format) is an XML format used in ROS to describe a robot’s physical configuration. It defines the robot's **links**, **joints**, **geometry**, **inertia**, and other properties needed for simulation, visualization, and motion planning.

URDF allows ROS to understand:

- How your robot moves  
- How it interacts with its environment  
- How to visualize it in tools like **RViz** or **Gazebo**

---

## Core Concepts

### 1. Links

- **Links** represent the rigid parts of a robot.  
- Each link has properties like **visual**, **collision**, and **inertia**.  

**Example:**
```xml
<link name="base_link">
  <visual>
    <geometry>
      <box size="0.5 0.5 0.2"/>
    </geometry>
    <material name="blue"/>
  </visual>
  <collision>
    <geometry>
      <box size="0.5 0.5 0.2"/>
    </geometry>
  </collision>
  <inertia ixx="0.1" iyy="0.1" izz="0.1" ixy="0.0" ixz="0.0" iyz="0.0"/>
</link>
```

### 2. Joints

- **Joints** define how links are connected and move relative to each other.

- Common joint types:
  - `revolute` – rotates around an axis
  - `prismatic` – slides along an axis
  - `fixed` – no movement

**Example:**
```xml
<joint name="base_to_wheel" type="revolute">
  <parent link="base_link"/>
  <child link="wheel_link"/>
  <origin xyz="0 0 0" rpy="0 0 0"/>
  <axis xyz="0 1 0"/>
</joint>
```

### 3. Visual & Collision

- **Visual**: How the robot looks in RViz or Gazebo.
- **Collision**: Geometry used for detecting collisions during simulation or planning.
- Both can have shapes like box, cylinder, sphere, or mesh files (.dae, .stl).

### 4. Origin

- **Origin**: Defines the position (xyz) and orientation (rpy) of a link or joint relative to its parent.

**Example:**
```xml
<origin xyz="0.1 0 0.2" rpy="0 0 1.57"/>
```

### 5. Inertia

- **Inertia**: Describes mass distribution of a link for physics simulation.
- Required for dynamic simulations in Gazebo.

**Example:**
```xml
<inertia ixx="0.1" iyy="0.1" izz="0.1" ixy="0" ixz="0" iyz="0"/>
```

### 6. Materials

- **Materials**: Define colors or textures for visualization.

**Example:**
```xml
<material name="red">
  <color rgba="1 0 0 1"/>
</material>
```

---

## Key Features

- **Comprehensive URDF Examples:** Includes practical implementations of links, joints, visual and collision geometry, origin tags, inertia, and materials.  
- **Beginner-Friendly:** Clear, commented examples ideal for ROS2 beginners to understand robot modeling concepts.  
- **Link–Joint Structures:** Demonstrates proper hierarchical structuring of links and joints for accurate robot kinematics.  
- **Visual & Collision Modeling:** Shows how to define both visual appearance and collision geometry for simulation and planning.  
- **Physics-Ready Inertia:** Provides correct inertia specifications for dynamic simulations in Gazebo.  
- **Material & Color Definitions:** Demonstrates how to use materials and colors for better visualization in RViz and Gazebo.  
- **Simulation-Ready:** All examples can be directly visualized in **RViz** or loaded into **Gazebo** for testing.  

---

## Learning Outcomes

By exploring this repository, you will learn:

1. **URDF Fundamentals:** Understand how robots are described in ROS2 using XML-based URDF format.  
2. **Robot Modeling:** Gain hands-on experience creating links, joints, origins, and hierarchical robot structures.  
3. **Visual vs Collision Geometry:** Learn the difference and how to define them correctly for simulation and planning.  
4. **Inertia & Physics:** Understand the role of inertia and mass properties for realistic dynamic simulations.  
5. **Using Materials:** Learn to assign colors and textures to links for better visualization.  
7. **Simulation Integration:** Understand how URDF integrates with RViz and Gazebo for visualization and simulation.  
8. **Practical Robot Design:** Build the foundational skills needed to design robots for motion planning, navigation, and ROS2-based projects.  

---

## Installation

### Make Workspace
```bash
mkdir robot_ws/
```

### Change Workspace
```bash
cd robot_ws
```

### Make src
```bash
mkdir src/
```

### Change Workspace
```bash
cd src
```

### Clone This Repository
```bash
git clone https://github.com/yashbhaskar/ROS2-URDF.git
```

### Change Workspace
```bash
cd ..
```

### Build the Package
```bash
colcon build --packages-select urdf_pkg
source install/setup.bash
```

---

## 🚀 How to Run

To easily view and simulate URDF files while coding, we recommend using the **URDF Visualizer extension** in **VS Code**. This makes robot modeling faster and more interactive.

### Steps:

1. **Install VS Code** (if not already installed)  
2. **Install URDF Visualizer Extension**:  
   - Open VS Code  
   - Go to **Extensions** (`Ctrl+Shift+X`)  
   - Search for **URDF Visualizer**  
   - Click **Install**  
<img width="1458" height="446" alt="Screenshot from 2026-01-09 16-56-54" src="https://github.com/user-attachments/assets/33aaf04b-9763-4103-9e18-9fc843248f43" />

3. **Open Your URDF/Xacro File** in VS Code  
4. **Launch the URDF Visualizer**:  
   - Click the **Tap icon** at the top-right corner of the VS Code editor  
   - A 3D preview of your robot will open  
   - You can **rotate, zoom, and pan** to inspect links, joints, and collision geometry  
   - Any changes in your URDF/Xacro file are **instantly reflected** in the preview  

### Example:

> Using the Tap icon helps quickly check **link geometry, joints, materials**, and **collision shapes**, reducing errors before simulation in RViz or Gazebo.
<img width="1843" height="1052" alt="Screenshot from 2026-01-09 16-54-07" src="https://github.com/user-attachments/assets/71c7f98b-575d-48db-bea0-873cf7731c65" />
<img width="1843" height="1052" alt="Screenshot from 2026-01-09 16-54-42" src="https://github.com/user-attachments/assets/fcfed065-a9e1-468a-9e49-668c9138610b" />
<img width="1843" height="1052" alt="Screenshot from 2026-01-09 16-55-07" src="https://github.com/user-attachments/assets/7c92f0eb-e84c-4167-b30a-1bc8ba1e4945" />

---

## ✉️ Contact

📧 Yash Bhaskar – ybbhaskar19@gmail.com

📌 GitHub: https://github.com/yashbhaskar
