----------------------------------------------------------------------------------
Concrete And Steel Dedicated Server (CNSDS)
(c) 2016 Russell Vincent Peterson / Matterhorn Software LTD
----------------------------------------------------------------------------------

Last updated for version v1.0rc5

----------------------------------------------------------------------------------
Requirements
----------------------------------------------------------------------------------

Linux, Mac or Windows, 64 bit.

Concrete And Steel (Game)	App ID 444830
Concrete And Steel (Server)	App ID 471180

Either Game or Server versions of Concrete And Steel can be invoked as a dedicated 
server.

However, for operational and performance reasons reasons, Linux dedicated servers 
running in a professional environment should use app ID 471180.

In this document we will refer to the Linux build in app ID 471180 rather than the 
Linux version in app id 444830.

----------------------------------------------------------------------------------
Instructions
----------------------------------------------------------------------------------

At the very least, all you need to do is run:

Linux	:	cnsds.x86_64 -batchmode
Mac		:	ConcreteAndSteel.app -batchmode
Windows	:	ConcreteAndSteel.exe -batchmode

This will get all of the server variables from "dedicated_server.xml" in the root 
directory, and load mods from ./cnsds_Data/StreamingAssets/


You may also specify an instance id:

Linux	:	cnsds.x86_64 -batchmode id=example_server
Mac		:	ConcreteAndSteel.app -batchmode id=example_server
Windows	:	ConcreteAndSteel.exe -batchmode id=example_server

This will look in ./example_server/ for "dedicated_server.xml" and will load mods 
from ./example_server/mods/

----------------------------------------------------------------------------------
Configuration using dedicated_server.xml
----------------------------------------------------------------------------------

<cnsds>
	<config
		name="Concrete And Steel Dedicated Server" 
		port="65433" 
		map="FlatGrass" 
		broadcast="true" 
		build_password="" 
		autosave="true" 
		autosave_minutes="10" 
		autosave_name="default" 
	/>
</cnsds>

name (string)			: The display name of this server
port (int)				: The port the server will listen on
map (string)			: The map to load
broadcast (true|false)	: Should this server be in the "Join Game" list?
build_password (string)	: The password players will need to be able to build.
autosave (true|false)	: Should the server autosave?
autosave_minutes (int)	: How often should the server autosave?
autosave_name (string)	: What name should we use for the savegame? 

----------------------------------------------------------------------------------
Map Names (as of v1.0rc5)
----------------------------------------------------------------------------------

FlatGrass
FlatGrassNight
FlatSand
FlatSnow
Moon
Mars
River
SkyScraper
Shipwrecked
Tutorial

----------------------------------------------------------------------------------
Savegame Name Format And Location
----------------------------------------------------------------------------------

If an ID is specified, autosave will write to:
./<ID>/[map]_savegame_[autosave_name].xml

Where <ID> is the ID we specified when launching the binary.

Otherwise, it will generate the savegame file in the root dir:
./[map]_savegame_[autosave_name].xml

----------------------------------------------------------------------------------
Further Information and Support
----------------------------------------------------------------------------------
Help can be found on our forum: http://forum.concreteandsteel.net/

Or Email russ@m.digital / Skype helical.russ

