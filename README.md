# finiteelement

A structural Finite Element Method MATLAB program taking in standard format input and boundary_conditions files. Output is the displacement vector.

## 1. Prepare an input.txt file

The structure of the input file is as follows

..a. There are 15 columns separated by spaces and (No. of Elements + 1) rows.

..b. The first two columns of the first row have the number of elements (NEL) and the no of nodes (No_Nodes) followed by thirteen zeros

..c. Every row that follows has the following format:

...1. Element Number (Elno)
...2. The smaller node number (i)
...3. The bigger node number (j)
...4. x component of the consistent nodal force vector on the first node (Fxi)
...5. y component of the consistent nodal force vector on the first node (Fyi)
...6. Moment on the first node (NOT USED BY THE PROGRAM) (Mi)
...7. x component of the consistent nodal force vector on the second node (Fxj)
...8. y component of the consistent nodal force vector on the second node (Fyj)
...9. Moment on the second node (NOT USED BY THE PROGRAM) (Mj)
...10. Elastic modulus of the element (E)
...11. Cross-sectional area of the element (A)
...12. Moment of Inertia of the bar element (NOT USED BY THE PROGRAM) (I)
...13. Length of the element (L)
...14. Height of the element (NOT USED BY THE PROGRAM)(h)
...15. Orientation of the element (α)

```
NEL No_Nodes 0 0 0 0 0 0 0 0 0 0 0 0 0
ELno i j Fxi Fyi Mi Fxj Fyj Mj E A I L h α
…
…
```

2. Prepare the input_geometry.txt file

The structure of the input file is as follows
```
NEL NNodes 0 0 0 0 0
Elno i j xi yi xj yj
…
…
```
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
