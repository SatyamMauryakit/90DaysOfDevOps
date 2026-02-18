# Day 09 Challenge – Linux User & Group Management

## Users & Groups Created
Users:
- tokyo
- berlin
- professor
- nairobi

Groups:
- developers
- admins
- project-team

## Group Assignments
- tokyo → developers, project-team  
- berlin → developers, admins  
- professor → admins  
- nairobi → project-team  

## Directories Created
- /opt/dev-project → group: developers → permission: 775  
- /opt/team-workspace → group: project-team → permission: 775  

## Commands Used
sudo useradd -m tokyo  
sudo useradd -m berlin  
sudo useradd -m professor  
sudo useradd -m nairobi  

sudo passwd tokyo  
sudo passwd berlin  
sudo passwd professor  
sudo passwd nairobi  

sudo groupadd developers  
sudo groupadd admins  
sudo groupadd project-team  

sudo usermod -aG developers tokyo  
sudo usermod -aG developers,admins berlin  
sudo usermod -aG admins professor  
sudo usermod -aG project-team tokyo  
sudo usermod -aG project-team nairobi  

sudo mkdir /opt/dev-project  
sudo chgrp developers /opt/dev-project  
sudo chmod 775 /opt/dev-project  

sudo mkdir /opt/team-workspace  
sudo chgrp project-team /opt/team-workspace  
sudo chmod 775 /opt/team-workspace  

sudo -u tokyo touch /opt/dev-project/tokyo.txt  
sudo -u berlin touch /opt/dev-project/berlin.txt  
sudo -u nairobi touch /opt/team-workspace/nairobi.txt  

## What I Learned
- How to create Linux users and groups  
- How to assign multiple groups to a user  
- How to use group permissions for shared directories  

groups tokyo
groups berlin
groups professor
groups nairobi

ls -ld /opt/dev-project
ls -ld /opt/team-workspace
