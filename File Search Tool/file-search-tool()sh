#!/bin/bash

echo "=============================="
echo "       File Search Tool"
echo "=============================="

# Ask for filename
while true
do
    read -p "Enter filename (ex. report.txt): " filename

    if [ -z "$filename" ]; then
        echo "Filename cannot be empty. Please try again."
    else
        break
    fi
done

echo
echo "Searching..."
sleep 1

# Search inside Home directory
result=$(find ~ -name "*$filename.*" 2>/dev/null)

echo

if [ -z "$result" ]; then
    echo "=============================="
    echo "      FILE NOT FOUND"
    echo "=============================="
    echo "No file named '$filename' was found."
else
    echo "=============================="
    echo "       FILE FOUND!"
    echo "=============================="
    echo "Location:"
    echo "$result"
fi

echo
echo "Search Complete."
