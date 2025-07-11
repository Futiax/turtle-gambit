# Turtle Control
You can go to [localhost:3000](https://localhost:3000) which will show your turtle.
Controls
- W ( Forward )
- S ( Backwards )
- A ( Turn Left )
- D ( Turn Right )
- Space ( Up )
- Left Shift ( Down )

# Turtle Cost
- 7 smooth stone
- 7 iron ingots
- 3 diamonds
- 2 logs
- 1 glass pane
- 1 redstone

### Mitosis
> Note: This process is still a bit messy and not currently supported, it is recommended to do this manually
#### Materials needed
- Mining turtle
- Disk Drive
- Floppy Disk



### Fork of [ottomated/turtle-gambit](https://github.com/ottomated/turtle-gambit) and [Sharmasrijan1/turtle-gambit](https://github.com/Sharmasrijan1/turtle-gambit)

I use Sharmasrijan1 patch to update the dependencies as most of the current dependencies of the [ottomated/turtle-gambit](https://github.com/ottomated/turtle-gambit) repo is no longer maintained or supported, which causes issues during installation.

# Usage
### Prerequisites
- NodeJS
- Yarn Package manager
> Note: The bottom 2 are optional but are recommended if there is more than 1 turtle
- GPS Cluster in world [Setup Instructions](http://www.computercraft.info/forums2/index.php?/topic/3088-how-to-guide-gps-global-position-system/)
- Turtle with modem

### Setup
#### Package installation
The first step is to download the node packages, to do this run `yarn` in the repo folder. After successfully downloading the packages go into the `frontend` folder and run the `yarn` command again.

#### Pastebin setup
Next you need to setup your turtle script, it is recommended that you have a pastebin account so you are able to edit the paste in the future. Copy the script from `startup.lua` into pastebin, but before uploading it you need to make some changes. Find the line which declares the `websocketServer` variable, you need to change that to your ip address if you are portforwarding or if you are using a tunneling service change it to the address which has been assigned to you.

#### Getting the pastebin ID
After uploading your new script copy the pastebin id from the url, it should be a 8 character long alphanumerical string.
For example if the url is `https://https://pastebin.com/fVQuK8nv`
The pastebin id would be `fVQuK8nv`
This will be needed later so just keep that in your clipboard or in notepad.

#### Starting up the servers
The first server you will be starting up is the backend server which is located in the repo folder. To start it run the command `yarn dev`, if it starts up successfully you should see the console saying `Started Turtle Control WS Server on port 5757 and port 5758` which means the server has started. Now to run the frontend server you need to go into the `frontend` folder and run the same command again `yarn dev`. After that the frontend server should have successfully started up, to confirm this go to [localhost:3000](https://localhost:3000) which will show a gray screen ( this is expected ).

#### Connecting your turtles
> Note: if you are connecting to localhost ComputerCraft may block the connection as localhost is not allowed on default, this can be fixed by changing your ComputerCraft config file https://github.com/cc-tweaked/CC-Tweaked/discussions/626

Now go to your turtle terminal and type in the command `pastebin get <YOUR PASTEBIN ID> startup` . Replace the `<YOUR PASTEBIN ID>` with the pastebin ID you had created, after that run the `reboot` command, once it finished rebooting you would see the terminal saying `Turtle Control OS, originally created by Ottomated. Modified by PrintedScript`, which has mean you have successfully connected your turtle! 🎉🎉

#### Setup
First you need to clone your turtle startup script onto your floppy disk, you can do this by running the command from any computer or turtle which is connected to the disk drive
`pastebin get <YOUR PASTEBIN ID> disk/startup`
Once done place your floppy disk and disk drive into your turtle

#### Cloning
Before going through mitosis make sure your turtle has fuel in its first slot and another turtle in its inventory, now you can click the `UNDERGO MITOSIS` button and your turtle should start placing down its disk drive and the new turtle. After a few seconds you should see a new turtle appear in your control panel, which means your turtle has successfully connected to your server.

### Troubleshooting
#### Location is at 0,0,0
Make sure your turtle has fuel in it as it is needed to determine its direction. Put any type of fuel source in its inventory, then on the control panel click that slot and then click the refuel button, after that click the refresh info button and the turtle will attempt to recalibrate its position and direction.

#### ERR_PACKAGE_PATH_NOT_EXPORTED
As of now I have not figured out how to fix this issue and seem to only appear on Windows machines, if you do know how to fix this issue please create a new issue and I will try to add it to this README