                        TASK 7: Monitor System Resources Using Netdata

STEP 1: Launch EC2 Instance
•	AMI: Amazon Linux (Kernel 5.10)
•	Instance Type: t2.micro
•	EBS Volume: 8GB
________________________________________
STEP 2: Install Docker 
yum install docker -y
systemctl start docker
systemctl status docker
________________________________________
STEP 3: run the Netdata

Cmd: docker run -d --name=netdata -p 19999:19999 netdata/netdata
________________________________________
STEP 4: access the server using the url which we get after running the netdata 
URL: http://54.235.59.35:19999
________________________________________
Step 5: Install stress 
# Step 1: Enable EPEL repository (Extra Packages for Enterprise Linux)
    Cmd:  sudo amazon-linux-extras install epel -y

# Step 2: Install stress
     Cmd: sudo yum install stress -y

Apply stress: 
   Cmd:  stress --cpu 1 --timeout 60
 --cpu 4: Starts 4 CPU workers (adjust based on how much stress you want).
 --timeout 60: Runs for 60 seconds.

________________________________________
STEP 6: before applying stress

output:
 
![image](https://github.com/user-attachments/assets/5468b721-709f-479c-9c91-7ceffb7652d1)


After applying stress:
output:
 
![image](https://github.com/user-attachments/assets/4ebc82cc-f48e-457c-8b5b-a05af5411b60)

