Multiclass Server Installation Guide
============================================================

1. PEQ Database Setup
Download the PEQ Backup - Found in assets folder of your server files
The file thj_peq_backup.sql contains the PEQ database required for this server.

Importing the Database
Open a Command Prompt.

Navigate to the folder containing thj_peq_backup.sql.

Run the following commands:


mysql -u root -p -e "CREATE DATABASE thj_peq;"
mysql -u root -p thj_peq < thj_peq_backup.sql

Login Credentials:
For out‑of‑the‑box compatibility, set your MySQL login and password to:
user: root
password: root
If you choose a different password, you must update it in the following files:

eqemu_config.json
login.json
quests\migrate_bags.pl
quests\migrate_items.pl

============================================================

2. Client Setup

Download the Multiclass-Server Client Files from the GitHub release page:

https://github.com/Kraqurjak/Multiclass-Server-Release/releases/tag/V1.0

Install the RoF2 Client
Download the RoF2 client from Steam or another source.
(Exact links cannot be provided for copyright reasons.)

Extract the Multiclass-Server Client Files.
Copy them into your RoF2 folder.
Overwrite all files when prompted.

Configure eqhost.txt
If you are running locally, set:

[LoginServer]
Host=127.0.0.1:5999
If you are connecting to a remote server, change the host to match your server's IP and port.

Your client is now ready.

============================================================

3. Server Setup

Download the Server-Packet from the GitHub release page:

https://github.com/Kraqurjak/Multiclass-Server-Release/releases/tag/V1.0

This package includes:

quests
plugins
spire
all required server scripts

Build the Server:
Run CMake to generate project files.
Compile the server in Release Mode using Visual Studio.
Copy your compiled bin folder into the Server-Packet directory.

Important: zlib-ng1.dll
Do not overwrite the zlib-ng1.dll included in the Server-Packet.
The server requires this specific version.

A backup copy is included in:
Server-Packet/zlib-ng1 Backup/
If you accidentally delete or overwrite it, copy the backup into your bin directory.

Final Step
Run the server executables, or spire
If your database and configs are correct, the server should start normally.