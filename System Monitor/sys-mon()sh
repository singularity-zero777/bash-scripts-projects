Okay editted it:
while true
do
 echo "=============================="
 echo "     System Monitor"
 echo "=============================="

 echo
 echo "1) Current User"
 echo "2) Current Directory"
 echo "3) Current Date"
 echo "4) Disk Usage"
 echo "5) Memory Usage"
 echo "6) Exit"

 read -p "Choose option (1-6): " choice

 echo
 echo "Loading,..."
 sleep 1
 echo
 echo "=================="
 echo "     RESULTS"
 echo "=================="
 echo

 case $choice in
    1)
        whoami
        ;;
    2)
        pwd
        ;;
    3)
        date
        ;;
    4)
        df -h
        ;;
    5)
        free -h
        ;;
    6)
        echo "Exiting system Monitor.."
        break
        ;; 
    *)
        echo "Invalid option."
        ;;
 esac

 echo
 sleep 1

 read -p "Press Enter to return to the menu...."
 clear
done

