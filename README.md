
 Linux Installation & ROS2 Setup

This repository contains the documentation and pictorial report for installing and running the Robot Operating System (ROS2) on a Linux environment configured via Windows.

##  🛠️ Environment Details
- Linux Distribution: Ubuntu (Noble / 24.04)
- ROS2 Version: Jazzy Jalisco

---

## 📋 Installation Steps & Proof

### 1. Setting up Linux on Windows (WSL2 & Ubuntu)

- Enabled the Windows Subsystem for Linux and installed Ubuntu from the Microsoft Store.
- Configured the terminal environment and root access.

### 2. Adding ROS2 Repositories & Keys

Updated system packages and configured software properties:

```bash
apt install software-properties-common curl -y
add-apt-repository universe -y
Added the official ROS2 GPG key and repository source list.
3. Installing ROS2 Desktop
Installed the complete desktop package compatible with the system distribution:
apt update
apt install ros-jazzy-desktop -y
Configured the environment setup path in .bashrc:
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc
4. Verification & Testing
Checked the active ROS distribution variable:
echo $ROS_DISTRO
Tested node communication by running the C++ talker node:
ros2 run demo_nodes_cpp talker
(Successfully published Hello World streams and terminated using Ctrl + C).

⚠️ Challenges Faced & Solutions
Package Location Mismatch (Humble vs. Noble):
Problem: Initially, the system couldn’t locate the older ros-humble-desktop package due to an incompatibility with the newer Ubuntu distribution version (Noble 24.04).
Solution: Switched and upgraded the installation to the fully compatible and modern ROS2 Jazzy version.
Command Syntax Adjustments:
Problem: Encountered unrecognized argument errors when verifying via standard version flags.
Solution: Verified the environment properly using environment variables like echo $ROS_DISTRO and running functional test nodes.
