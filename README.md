## StayKit - Cobalt Strike persistence kit

StayKit is an extension for Cobalt Strike persistence by leveraging the execute_assembly function with the SharpStay .NET assembly. The aggressor script handles payload creation by reading the template files for a specific execution type. 

IMPORTANT: To use the script a user will only need to load the `StayKit.cna` aggressor script. Additionally, the [SharpStay](https://github.com/0xthirteen/SharpStay) assembly will need to be compiled and placed into the directory where `StayKit.cna` is located. Finally, if selecting a template for the payload some may require dynamic compiling which will uses Mono.

The persistence menu will be added to the beacon. Due to the nature of how each technique is different there is only a GUI menu and no beacon commands. 

Available options:

 * ElevatedRegistryKey
 * UserRegistryKey
 * UserInitMprLogonScriptKey
 * ElevatedUserInitKey
 * ScheduledTask
 * ListScheduledTasks
 * ScheduledTaskAction
 * SchTaskCOMHijack
 * CreateService
 * ListRunningServices
 * WMIEventSub
 * GetScheduledTaskCOMHandler
 * JunctionFolder
 * StartupDirectory
 * NewLNK
 * BackdoorLNK
 * ListTaskNames


#### Dependencies
  * Mono (MCS) for compiling .NET assemblies (Used with dynamic payload creation) 


#### Credits
  * WMI Event Subscription - WQL Query from [Empire Project](https://github.com/EmpireProject/Empire) and [Matt Graeber's](https://twitter.com/mattifestation) research
  * Scheduled Task COM Handler Hijack - idea from [enigma0x3's](https://twitter.com/enigma0x3) research
  * Junction Folder - code and idea comes from [matterpreter's](https://twitter.com/matterpreter) OffensiveCSharp project
  * Backdoor LNK - comes from [harmj0y's](https://twitter.com/harmj0y) LNKBackdoor script