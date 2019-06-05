# Arma3-target-popup  
This is a customized version on FoxRazgriz/SSgt Schirf 's popup.sqf.  
Suitble for clan killing house usage  
tested on a clan server  
# Syntax for using  
1. each target has a name like target_1  
//those code for executing reset action  
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
  
# 适用于战队训练场的靶场不弹起和统一复位脚本  
（服务器化改造的单机脚本）  
0. 安装脚本至你的任务  
1. 添加如下代码至复位用物品（任一行）  
其中target_x为一个所有需要复位的靶子的变量列表  
this addAction ["复位靶场",{[[target_1,target_2,target_3],0,1,true] ExecVM  "popup.sqf";}]  
this addAction ["复位靶场",{[[[target_1,target_2,target_3],0,1,true],"popup.sqf"] remoteExec ["execVM",0];}]  
2. 对每一个靶子添加一个不同的变量名如target_1, 在初始化区域添加如下代码防止自动弹起  
this setVariable ["nopop",true,true];   
this setVariable ["nopop",true,true];   
this addEventHandler ["hitpart", {   
_this spawn {  
  waituntil {(_this select 0 select 0) animationPhase "terc" ==1};   
  waituntil {(_this select 0 select 0) animationPhase "terc" <1};   
 (_this select 0 select 0) animate ["terc",1];   
}}];   
