1. Create a new server assumed as a jenkins slave
apt-get update
apt-get install openjdk-8-jdk -y

2. Ensure that jenkins master can ssh into jenkins slave
-- Generate a new key-pair in the master with "ssh-keygen" command
-- Copy .ssh/id_rsa.pub from master to .ssh/authorized_keys of the slave
-- "ssh root@slave-ip" to ensure that the authentication is actually working

3. Configure the slave in jenkins UI
-- Manage Jenkins > Manage nodes and clouds > New Node (left hand nav) and add the details.
-- Jenkins is also going to require "credentials" that it can use to connect to the slave. Add every details except the credentials and save the page for now.
-- Goto Jenkins Home > Credentials > System > Global Credentials > Add credentials and fill in the details including your private key.
-- Go back to the jenkins slave configuration and set it to use the credentials that you just created > save
-- Click on "re launch agent" and that should finish the setup.