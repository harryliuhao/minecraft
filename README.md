# minecraft
Refresh steps:
1. Download server.jar from minecraft.com
2. rename server.jar to a version name, like "minecraft_server.1.14"
3. Upload the jar to hao-minecraft-download bucket
4. Go to EC2, create a image of stopped server
5. start the old server. Use the new ip to ssh to the instance
6. copy the file to ec2: aws s3 cp s3://hao-minecraft-download/minecraft_server.1.14.jar minecraft_server.1.14.jar
7. update mc.sh with the new jar file name or directly execute: java -Xmx1024M -Xms1024M -jar minecraft_server.1.14.jar nogui
