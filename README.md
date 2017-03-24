# finiteelement
Code formulating Finite Element Method code usingMATLAB

Input strategy for pre-processor

Step 1: Prepare the “input.txt” file: The structure of the input file is as follows
NEL NNodes 0 0 0 0 0 0 0 0 0 0 0 0 0
ELno i j Fxi Fyi Mi Fxj Fyj Mj E A I L h α
…
…
First line of the ‘input.txt’ file is used to enter the total number of elements (NEL) and the total
number of nodes (NNodes). The rest of this line should be filled with (13) zeros.
• Lines following the first line are used to enter element connectivity table and the element
properties.


Step 2: Prepare the “input_geometry.txt” file: The structure of the input file is as follows,
NEL NNodes 0 0 0 0 0
Elno i j xi yi xj yj
…
…
• First line of the ‘input_geometry.txt’ file is used to enter the total number of elements (NEL) and
the total number of nodes (NNodes). The rest of this line should be filled with 6 zeros.
• Lines following the first line are used to enter the coordinates (xi,yi) and (xj,yj) of the nodes-I
and –j of the element with respect to the global coordinate system.


Step 3: Prepare the boundary conditions file: The structure of the boundary conditions input file:
NBCs 0 0
Node BC_dof BC_magnitude
… … …
• NBCs: Total number of BCs that we want to impose, followed by 2 zeroes.
• Node: The node number at which the BC is to be imposed
• BC_dof:
o 1: to impose a BC for u, OR,
o 2: to impose a BC for v, OR,
o 3: to impose a BC for θ
• BC_magnitude: The magnitude of the imposed BC.
• This file should contain NBC+1 lines.
