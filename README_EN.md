# FQsolverData
Data for FQsolvers, which can be found at https://github.com/light-chen-light/FQsolvers

## How to read file names:
Each file name consists of three parts.
* File upload date
* Event name
* Version of FQsolver corresponded

For example, 20210127kamakuraM1 is the data file uploaded on Janurary 27th, 2021 for the Kamakura event, designed for FQ solver Version M1

## How to use/what's in the file:
* Download the needed data file to your MATLAB/Octave folder
* Load the file with MATLAB command "load"
* * MissionName is a m×1 cell matrix, consisting of the names of the mission requirements
* * Mission is a m×1 double matrix, consisting of the quantities of the mission requirements.
* * FQName is a n×1 cell matrix, consisting of the names of the free quests.
* * AP is a n×1 cell matrix, consisting of the AP costs of the free quests.
* * (M1) Contr is a m×n double matrix, consisting of the contribution of each free quest toward each mission.
* * (M2) ContrCommon is a m×n double matrix, consisting of the contribution of all non-rare enemies in each free quest toward each mission.
* * (M2) ContrRare is a m×n double matrix, consisting of the contribution of all rare enemies in each free quest toward each mission.
* * (M2) Rare is a 1x1 double, referring to the default odd that a rare enemy shows up (in percentage); or if more than 1 rare enemy can show up, it denotes the expected value of number of rare enemies. You should adjust it due to the craft essences your party equips. See more in "Tips."
* Create a variable "Reach" that reflect your progress. You might want to start with either of the following and then adjust later:
* * Reach=zeros(size(Mission));
* * Reach=Mission;
* Use the FQsolver

## Tips
* You can adjust AP with your preference: slightly lower the AP of the quests you like, slightly raise the AP of the quests you don't lke, and raise the AP skyhigh if you don't want to touch it at all.
* You can fully costumize the vector AP if you have a different criterion for efficiency (lower numbers means more acceptable quests, etc., while the numbers should be positive)
* (M2) You should adjust Rare due to the craft essences your party equips, or due to other factors if you wish to. However, if you wish to set Rare as 0, remember to adjust Reach so that any mission that specifically requires rare enemies is set as done.
* Enter and run this code to display a summary of missions
* * cat(2,MissionName,mat2cell(Mission,ones(1,length(Mission))),mat2cell(Reach,ones(1,length(Reach))))
* Enter and run this code to display a summary of quests
* * cat(2,FQName,mat2cell(AP,ones(1,length(Mission))))
