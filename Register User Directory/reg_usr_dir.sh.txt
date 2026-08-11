#!/bin/bash

echo "================================"
echo "    User Directory Generator"
echo "================================"

read -p "Enter employee name: " username

echo
echo "Choose a department:"
echo "1) IT"
echo "2) HR"
echo "3) SALES"
echo "4) MARKETING"
echo "5) ACCOUNTING"

read -p "Enter choice (1-5): " deptchoice

case $deptchoice in
    1) dept="IT" ;;
    2) dept="HR" ;;
    3) dept="SALES" ;;
    4) dept="MARKETING" ;;
    5) dept="ACCOUNTING" ;;
    *) echo "Invalid department."; exit 1 ;;
esac

echo
echo "Generating directories..."
sleep 1

mkdir "$username"
mkdir "$username/UserFiles"
mkdir "$username/UserFiles/Documents"
mkdir "$username/UserFiles/Reports"
mkdir "$username/UserFiles/Logs"
mkdir "$username/UserFiles/Downloads"

echo
echo "=============================="
echo " Directory Created Successfully"
echo "=============================="
echo "Employee : $username"
echo "Department : $dept"
echo
echo "Folders Created:"
echo "- Documents"
echo "- Reports"
echo "- Logs"
echo "- Downloads"
