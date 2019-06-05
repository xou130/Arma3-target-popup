# Arma3-target-popup  
This is a customized version on FoxRazgriz/SSgt Schirf 's popup.sqf.  
Suitble for clan killing house usage  
tested on a clain server  
# Syntax for using  
1. each target has a name like target_1  
[[target_1,target_2,target_3],0,1,true] ExecVM  "popup.sqf"  
[[[target_1,target_2,target_3],0,1,true],"popup.sqf"] remoteExec ["execVM"];  

this addAction ["popup",{[[target_1,target_2,target_3],0,1,true] ExecVM  "popup.sqf";}]  
this addAction ["popup",{[[[target_1,target_2,target_3],0,1,true],"popup.sqf"] remoteExec ["execVM"];}]  
//can be used on dedicated server on a "Laptop"  

2. For each target init field them use this  
// these codes are for 1.92 env to prevent target popup, add to init for each target(thanks to PiepMGI for this solution)  
this setVariable ["nopop",true,true];   
this setVariable ["nopop",true,true];   
this addEventHandler ["hitpart", {   
_this spawn {  
  waituntil {(_this select 0 select 0) animationPhase "terc" ==1};   
  waituntil {(_this select 0 select 0) animationPhase "terc" <1};   
 (_this select 0 select 0) animate ["terc",1];   
}}];   

#中文
#适用于战队训练场的靶场不弹起和统一复位脚本
