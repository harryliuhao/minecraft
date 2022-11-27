# minecraft
Refresh steps:
1. Download server.jar from minecraft.com
2. rename server.jar to a version name, like "minecraft_server.1.14"
3. Upload the jar to hao-minecraft-download bucket
4. Go to EC2, create a image of stopped server
5. start the old server. Use the new ip to ssh to the instance  
5.1. 'sudo su' to assume super user
6. copy the file to ec2: aws s3 cp s3://hao-minecraft-download/minecraft_server.1.14.jar minecraft_server.1.14.jar
7. update mc.sh with the new jar file name and execute bash mc.sh (alternantive is directly execute: java -Xmx8G -Xms1G -jar minecraft_server.1.17.jar nogui)
8. Make sure ops.json wasn't blank from the update. If it was erased, download the backup from s3 bucket
nohup sudo java -Xmx1G -Xms1G -jar minecraft_server.1.17.jar
