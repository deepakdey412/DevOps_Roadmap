🧭 Linux Master Guide for DevOps (Beginner → Pro)
===================================================
    
🧱 Phase 1 — Linux Basics (Week 1)
----------------------------------

🎯 Goal: Learn to move around the Linux system.

 📂 Navigation Commands

    pwd            Show current folder path
    ls             List files & folders
    ls -l          Detailed file info
    ls -a          Show hidden files
    cd folder      Enter folder
    cd ..          Go one level back
    cd             Go to home directory
    

 📁 File & Folder Creation

    mkdir test        Create folder
    rmdir test        Remove empty folder
    touch file.txt    Create file
    rm file.txt       Delete file
    clear             Clear terminal
    

📌 Practice: Create folders, move between them, and delete them.

  

📄 Phase 2 — File Handling (Week 2)
-----------------------------------

Used daily for server configs & logs.

    cp file1 file2      Copy file
    mv file folder/     Move or rename file
    rm file             Delete file
    cat file            Show file content
    less file           Scroll large files
    head file           Show first lines
    tail file           Show last lines
    tail -f logfile     Live log monitoring
    nano file.txt       Edit file
    

🛠 DevOps engineers constantly monitor logs using tail -f.

  

🔐 Phase 3 — Permissions (Week 3)
---------------------------------

Important for server security.

    ls -l                 Show permissions
    chmod 755 file        Change permission
    chmod +x script.sh    Make executable
    chown user file       Change file owner
    

Permission meanings:

   r → Read
   w → Write
   x → Execute

  

👤 Phase 4 — Users & Processes (Week 4)
---------------------------------------

 👥 User Management

    sudo adduser devuser    Create user
    sudo passwd devuser     Set password
    

 ⚙️ Process Management

    ps aux        Show running processes
    top           Live process monitoring
    htop          Better monitoring view
    kill PID      Stop process
    kill -9 PID   Force kill
    

🛠 Used when apps hang or consume too many resources.

  

📦 Phase 5 — Package Management (Week 5)
----------------------------------------

Used when installing server software.

    sudo apt update
    sudo apt upgrade
    sudo apt install nginx
    sudo apt remove nginx
    

  

🌐 Phase 6 — Networking (Week 6)
--------------------------------

Used to debug server connection issues.

    ip a                 Show IP address
    ping google.com      Test internet
    netstat -tulnp       Show open ports
    curl google.com      Fetch website data
    wget fileurl         Download file
    

  

🤖 Phase 7 — Shell Scripting (Week 7–8)
---------------------------------------

Automation is DevOps power.

 📝 Create Script

    nano script.sh
    

 Example Script

    !/bin/bash
    echo "Hello DevOps"
    

 ▶️ Run Script

    chmod +x script.sh
    ./script.sh
    

 Learn Next

   Variables
   Loops
   Conditions
   Cron jobs

  

💽 Phase 8 — Disk & System Monitoring
-------------------------------------

Monitor server health and usage.

    df -h       Disk space usage
    du -sh      Folder size
    free -m     RAM usage
    uptime      System running time
    top         CPU & process usage
    htop        Better monitoring view
    
