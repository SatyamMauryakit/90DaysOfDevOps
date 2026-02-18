# Day 11 Challenge – File Ownership
Check Ownership
ls -l
Owner = user who owns file
Group = group associated with file


chown (Change Owner)
touch devops-file.txt
ls -l devops-file.txt

sudo useradd tokyo
sudo useradd berlin

sudo chown tokyo devops-file.txt
sudo chown berlin devops-file.txt

ls -l devops-file.txt

 – chgrp (Change Group)
touch team-notes.txt
ls -l team-notes.txt

sudo groupadd heist-team
sudo chgrp heist-team team-notes.txt

ls -l team-notes.txt

– Change Owner & Group Together
touch project-config.yaml
sudo useradd professor

sudo chown professor:heist-team project-config.yaml

mkdir app-logs
sudo chown berlin:heist-team app-logs

 – Recursive Ownership
mkdir -p heist-project/vault heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf

sudo groupadd planners
sudo chown -R professor:planners heist-project/

ls -lR heist-project/


– Practice Challenge
sudo useradd nairobi
sudo groupadd vault-team
sudo groupadd tech-team

mkdir bank-heist
touch bank-heist/access-codes.txt
touch bank-heist/blueprints.pdf
touch bank-heist/escape-plan.txt

sudo chown tokyo:vault-team bank-heist/access-codes.txt
sudo chown berlin:tech-team bank-heist/blueprints.pdf
sudo chown nairobi:vault-team bank-heist/escape-plan.txt

ls -l bank-heist/