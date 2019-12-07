query.dat -> LTL query command for LTL to Buchi Automata converter

Workspace Descriptor files:

(1) 2D: cfile_rec.dat

Input format:
nr - number of rows
nc - number of columns
nobs - no of obstacles
nobs coordinates - 'nobs' lines for obstacle coordinates
np - no of coordinates where a certain proposition is true 
np coordinates - 'np' lines mentioning the coordinates and the proposition true at it.

Example file:
10                    -----> nr
10                    -----> nc
5                     -----> nobs
1 2                   -----> nobs lines mentioning the co-odinates of the obstacles    
3 4
5 6
9 5
3 9
4                     -----> np
5 5 1                 -----> np lines mentioning the coord and the prop true at it(ex. at (5,5) , proposition 1 is true)   
6 6 2
2 2 3 
3 3 4

Similarly in 3D: cfile_rec3d.dat: Same as 2D just adding z axis to input

nx - x axis length 
ny - y axis length
nz - z axis length
nobs - no of obstacles followed by coordinates of obstacles
np - no of coordinates where a certain proposition is true followed by coordinates and the proposition true at it.
Example file:
10
10
10
5
1 2 1
3 4 1
5 6 2 
9 5 3
3 9 5
4
5 5 5 1
6 6 6 2
2 2 2 3
3 3 3 4

2D binaries: Compile djk-optimal-run.cpp and motion-planner-final.cpp using g++ command with flag -std=c++11 to generate the binaries djk-optimal-run and motion-planner-final(on Ubantu OS) . 
Ex. 
1. g++ -std=c++11 djk-optimal-run.cpp -o djk-optimal-run
2. g++ -std=c++11 motion-planner-final.cpp -o motion-planner-final

To run :
./djk-optimal-run cfile_rec.dat
./motion-planner-final cfile_rec.dat

Similarly for 3D binaries
./djk-optimal3d cfile_rec3d.dat
./motion-planner3d cfile_rec3d.dat

Requirements:
Install Spot-2.6 tool for LTL2TGBA converter
Copy the ltl2tgba file from the bin folder of spot installation and copy it to the current folder 
Check if the tool is working by running example command in the current folder:
./ltl2tgba --spin '<>p && <>q'. This should give us the Buchi automata transitions  

For generating the 3D results. Just run the file mainscript.sh

