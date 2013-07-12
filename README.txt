VPC - Valve Project Creator For XCode and Makefiles (Build: May 27 2013 11:24:00)
(C) Copyright 1996-2010, Valve Corporation, All rights reserved.

Source Path: <YOUR SOURCE PATH>
Target Platform: <CURRENT PLATFORM>

usage: vpc [options] <+/-/*project or group>

Examples:

 Single .vcproj generation:
   vpc +client /hl2     <-- Creates a Win32 .vcproj for the HL2 client.
   vpc +shaderapi /x360 <-- Creates a Xbox360 .vcproj for the shaderapi.

 Multiple .vcproj generation - Multiple Projects for Games and Platforms:
   vpc +client /hl2 /tf           <-- Creates ALL the Win32 .vcprojs for the HL2 and TF client.
   vpc +gamedlls /allgames        <-- Creates ALL the Win32 .vcprojs for client and server for all GAMES.
   vpc +tools -tier0 /win32 /x360 <-- Creates ALL the Win32 and Xbox360 .vcprojs for the tool projects but not the tier0 project.

 Use +/- to add or remove projects or groups.
 Use *   to add a project and all projects that depend on it.
 Use @   to add a project and all projects that it depends on.
 Use /h spew final target build set only (no .vcproj created).

 Further details can be found on Valve Internal Wiki on VPC.
 
--- OPTIONS ---
[/q]:          Quiet mode (quiet mode is automatically on if the VPC_QUIET environment variable is set)
[/v]:          Verbose
[/f]:          Force generate .vcproj, otherwise use crc checks
[/dp]:         Decorate project names with platform
[/testmode]:   Override output .vcproj file to be named 'test.vcproj'
[/srcctl]:     Enable source control integration

--- Help ---
[/h]:          Help
[/?]:          Help
[/platforms]:  Spew Platforms
[/games]:      Spew Games
[/projects]:   Spew Projects
[/groups]:     Spew Groups
[/properties]: Spew VS2005 Properties

--- Conditionals ---
[/profile]:    Set Reserved $PROFILE=1
[/retail]:     Set Reserved $RETAIL=1
[/callcap]:    Set Reserved $CALLCAP=1
[/fastcap]:    Set Reserved $FASTCAP=1
[/cert]:       Set Reserved $CERT=1
[/memtest]:    Set Reserved $MEMTEST=1
[/nofpo]:      Set Reserved $NOFPO=1
[/lv]:         Set Reserved $LV=1
[/demo]:       Set Reserved $DEMO=1
[/no_steam]:   Set Reserved $NO_STEAM=1
[/qtdebug]:    Set Reserved $QTDEBUG=1
[/no_ceg]:	  Set Reserved $NO_CEG=1
[/upload_ceg]: Set Reserved $UPLOAD_CEG=1

--- Other ---
[/mksln]:      <.sln filename> - make a solution file
[/p4sln]:      <.sln filename> <changelists...> - make a solution file based on
               the changelist. Changelists can be specific numbers, 0 or "default"
               for the default changelist, or "all" for all active changelists.
[/nop4add]:    Don't automatically add project files to Perforce
[/slnitems]:   <filename> - adds all files listed in <filename> to generated
               solutions
[/showdeps]:   Show an example dependency chain for each project that depends
               on your p4 change list(s).  Use with /p4sln.
[/checkfiles]: Check for the existence of files in $file commands. For debugging vpc files.
               Only works if the currrent directory is the project directory.
[/define:xxx]: Enable a custom conditional $XXX to use for quick testing in VPC files.