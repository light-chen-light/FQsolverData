# FQsolverData
Data for FQsolvers, which can be found at https://github.com/light-chen-light/FQsolvers

## How to read file names:
Each file name consists of three parts.
* File upload date
* Event name
* Version of FQsolver corresponded

For example, 20210126kamakuraM1 is the data file uploaded on Janurary 26th, 2021 for the Kamakura event, designed for FQ solver Version M1

## How to use/what's in the file:
* Download the needed data file to your MATLAB/Octave folder
* Load the file with MATLAB command "load"
* * MissionDes is a m×2 cell matrix. The first column lists the name of the requirements, and the second column lists the quantities.
* Generate variable "Mission" with this code, adjust the contents if needed
* * Mission = cell2mat(MissionDes(:,2));
* Create a variable "Reach" that reflect your progress. You might want to start with either of the following and then adjust later:
* * Reach=zeros(size(Mission));
* * Reach=Mission;
* Use the FQsolver
