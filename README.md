SamsChannelEditor
=================

SamsChannelEditor is a desktop application for editing a channel list from your Samsung TV. Now sorting channels should be much easier.


* Support Samsung C and D Series.
* Works with scm files directly.
* Support for multiple channels configurations:
  * map-AirD
  * map-AirA
  * map-CableD
  * map-CableA
  * map-SateD
  * map-CDTVVD
  * AstraHDPlusD
* Support for configuration files (read-only)
  * CloneInfo
  * SatDataBase
* Easy to use: Just drag & drop channels.

Installation
------------
There's no setup file, just download de binaries and execute the samschanneleditor.exe file. All files are avaiable here.

This application is written in C# so you need the .Net framework 2.0 (or newer) to be installed on your computer.
You can download here : [.NET Framework](http://msdn.microsoft.com/en-us/netframework)

Bad file size error
-------------------
Since version 0.9 you can define new sizes in SamsChannelEditor.exe.config. Just open with a text editor like notepad and add a new size for your file in section.

key: starts with "fs_" and after comes the channel file name (without "-" after map) value: is a number list separated by commas. Each number specifies a possible record size.

To calculate your record size:

* change extension .scm to .zip
* Extract all files.
* Select file you are opening and look the size in file properties.
* record size is a 1000 multiple (divide your size by 1000 or 2000)

### Example: ###

```xml
<appSettings> 
   <add key="fs_default" value="292,320" /> 
   <add key="fs_mapAirA" value="40,64" /> 
   <add key="fs_mapCableA" value="40,64" /> 
   <add key="fs_mapSateD" value="168,172,194" /> 
   <add key="fs_mapAstraHDPlusD" value="212" /> 
</appSettings>
```

Libraries & Resources used
--------------------------
[\#ziplib](http://www.icsharpcode.net/opensource/sharpziplib)  
[log4net](http://logging.apache.org/log4net)  
[Free Icons by Axialis Software](http://www.axialis.com/free/icons)  

License
-------
    Copyright (C) 2011  Ivan Masmitj� Dagas

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

Last changelog
--------------
### Version 0.11 ###

* Fixed channel names output. Names in Russian output correctly. Other languages must do so
* Channel data edit feature realized. You can edit channel name and favourites.

### Version 0.10 ###

* Applied a patch created by Andreas Winter to save sort order to file and restore after.
* Applied a patch created by Andreas Mayer to remove encrypted channels.

### Version 0.9 ###

* Moved record sizes to SamsChannelEditor.exe.config. Now are easy to add new record sizes for new models.

### Version 0.8 ###

* BUG [3468470] : Open map-SateD 144bytes length (LE37C670)
* MoveTo problems detected when out of range number is introduced.

### Version 0.7 ###

* Works on D Series
* Drag and Drop with auto scroll
* Added support for analog channels map-AirA and map-CableA
* Context menu: MoveTo
* Context menu: Renumber All
