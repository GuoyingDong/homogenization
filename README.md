# homogenization
Please cite the following article if you use this code in your publications:

Dong G, Tang Y, Zhao Y. A 149 Line Homogenization Code for Three-Dimensional Cellular Materials Written in matlab. ASME. J. Eng. Mater. Technol. 2018;141(1):011005-011005-11. doi:10.1115/1.4040555.

Homogenization code for 3D lattice structure. For more information you can visit http://www.intralatticepro.com/

![alt text](https://github.com/GuoyingDong/homogenization/blob/master/image/homogenization.JPG)

"homo3d.m" is to calculate the homogenized material property of 3d lattice structures.

"GenerateVoxel.m" is to generate the voxel model for homo3d.m.

"visual.m" is to plot the 3D Young's modulus surface indicating E along all directions.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To use homo3d.m :

CH = homo3D(lx,ly,lz,lambda,mu,voxel);

% lx       = Unit cell length in x-direction.

% ly       = Unit cell length in y-direction.

% lz       = Unit cell length in z-direction.

% lambda   = Lame's first parameter for solid materials.

% mu       = Lame's second parameter for solid materials.

% voxel    = Material indicator matrix.

% lambda = vE/(1+v)(1-2v), mu = E/2(1+v), E is Young's modulus, v is Poisson's ratio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To use GenerateVoxel.m :

[voxel,Density] = GenerateVoxel(n,address,radius);

% n       = the number of voxel along each axis.

% address = the file location of wireframe.

% radius  = the radius of the lattice structure.

% Density = the relative density of the lattices.

The predifined wireframe file can be found in the topology folder.

The length of the unit cell is 1.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To use visual.m :

visual(CH);

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Example:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[voxel,Density] = GenerateVoxel(40,'topology/grid.txt',0.1);

CH = homo3D(1,1,1,115.4,79.6,voxel);

visual(CH)

% the topology is 'grid', the model has 40 voxels along each axis.

% the radius is 0.1, the length of the unit cell is 1 as defined.

% lambda = 115.4, mu = 79.6, whcih is equivalent to E = 200, v= 0.3.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The result is:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Density = 8.5%

CH =

7.1876    0.3875    0.3875    0.0000   -0.0000    0.0000

0.3875    7.1876    0.3875   -0.0000    0.0000    0.0000

0.3875    0.3875    7.1876   -0.0000   -0.0000   -0.0000

0.0000   -0.0000   -0.0000    0.1489    0.0000    0.0000

0.0000    0.0000   -0.0000    0.0000    0.1489   -0.0000

0.0000    0.0000   -0.0000    0.0000   -0.0000    0.1489
    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Young's modulus surface:

![alt text](https://github.com/GuoyingDong/homogenization/blob/master/image/1.jpg)
