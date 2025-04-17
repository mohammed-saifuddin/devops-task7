Devops task7
Monitor System Resources Using Netdata on Windows


Install Netdata using Docker Desktop on a Windows system to visualize system and application performance metrics such as CPU, memory, disk I/O, and Docker container activity.

Tools Used:
- Netdata (Free, open-source system monitoring tool)
- Docker Desktop for Windows

Instructions:

1. Install Docker Desktop:
   - Download Docker Desktop from https://www.docker.com/products/docker-desktop
   - Install and launch Docker Desktop
   - Make sure it is running

2. Run Netdata using Docker:
   - Open Command Prompt (cmd) or PowerShell


   Docker: docker run -d --name=netdata -p 19999:19999 netdata/netdata

3. Access the Netdata Dashboard:
   - Open a web browser and go to:
     http://localhost:19999

   You will see real-time system metrics such as:
   - CPU usage
   - RAM usage
   - Disk I/O
   - Network usage
   - Docker container stats (if containers are running)

4. Explore Alerts and Chart Panels:
   - In the dashboard, click the bell icon (top-right corner) to view active or historical alerts
   - Use the sidebar or top-left search bar to explore various chart panels like:
     - System Overview
     - Memory
     - Network Interfaces
     - Applications (Docker, etc.)

5. Explore Logs (inside the container):
   - Open a terminal (cmd, PowerShell, or Windows Terminal)
   - Run this command to enter the Netdata container:

     docker exec -it netdata bash

   - Inside the container, navigate to the logs folder:

     cd /var/log/netdata

   - View log files such as:

     cat error.log
     cat health.log

Deliverables:
- A screenshot of the Netdata dashboard showing running metrics (CPU, memory, disk, etc.)
- Confirmation of alert panel access and log viewing

Note:
- Docker must be running before starting Netdata
- To stop the Netdata container:
  docker stop netdata

- To remove the Netdata container:
  docker rm -f netdata
