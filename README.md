# System-maintainence-bash-script

#!/bin/bash

# Purpose: Perform system update, disk cleanup, and system monitoring.

# Function to perform a system update
update_system() {
    echo "Starting system update..."
    sudo apt update && sudo apt upgrade -y
    if [ $? -eq 0 ]; then
        echo "System updated successfully!"
    else
        echo "System update failed!"
    fi
}

# Function to clean up disk space
clean_disk() {
    echo "Performing disk cleanup..."
    sudo apt autoremove -y && sudo apt autoclean -y
    if [ $? -eq 0 ]; then
        echo "Disk cleanup completed successfully!"
    else
        echo "Disk cleanup failed!"
    fi
}

# Function to monitor system
monitor_system() {
    echo "Monitoring system resources..."
    echo "==============================="
    echo "Disk Usage:"
    df -h
    echo "-------------------------------"
    echo "Memory Usage:"
    free -h
    echo "-------------------------------"
  
