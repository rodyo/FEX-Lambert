[![View Robust solver for Lambert's orbital-boundary value problem on File Exchange](https://www.mathworks.com/matlabcentral/images/matlab-file-exchange.svg)](https://www.mathworks.com/matlabcentral/fileexchange/26348-robust-solver-for-lambert-s-orbital-boundary-value-problem)

[![Donate to Rody](https://i.stack.imgur.com/bneea.png)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=4M7RMVNMKAXXQ&source=url)

# FEX-Lambert

A Lambert-orbital boundary value problem can be stated as
"Find the orbit/trajectory of a spacecraft that flies from position [r1] to [r2], taking a time [tf] and making [m] complete orbits before arriving at [r2]. "
The solution to each Lambert-problem is NOT unique; one can travel to [r2] via the long way or the short way, and for [m > 0] there are almost always two ellipses that satisfy the boundary conditions, so that [m > 0] has four distinct solutions.
This function solves any Lambert problem *robustly*. It can handle short-way solutions (the default), long way solutions (by passing negative [tf]), or left-branch (default) or right-branch (by passing negative [m]) solutions in case [m > 0]. It uses two separate solvers; the first one it tries is a new and unpublished algorithm developed by Dr. D. Izzo from the European Space Agency [1]. This version is extremely fast, but especially for larger [m] it still fails quite frequently. In such cases, a MUCH more robust algorithm is started (the one by Lancaster & Blancard [2], with modifcations, initial values and other improvements by R.Gooding [3]), which is a lot slower partly because of its robustness.

This routine can be compiled to increase its speed by a factor of 20-50, which is certainly advisable when an application using this function requires a great number of Lambert problems to be solved. The entire routine is written in embedded MATLAB, so it can be compiled with the emlmex() function. It is described in the function's comments how to accomplish this.

Tested on WinXP/32 and Ubuntu 9.10/32. Tested on MATLAB 2008a through 2009b. As compilation is always a troublesome affair, please let me know what sort of problems you encounter so I can try to improve the code for that.

References:
[1] Izzo, D. ESA Advanced Concepts team. Code used available in MGA.M, on http://www.esa.int/gsp/ACT/inf/op/globopt.htm. Last retreived Nov, 2009.
[2] Lancaster, E.R. and Blanchard, R.C. "A unified form of Lambert's theorem." NASA technical note TN D-5368,1969.
[3] Gooding, R.H. "A procedure for the solution of Lambert's orbital boundary-value problem. Celestial Mechanics and Dynamical Astronomy, 48:145–165,1990.

If you like this work, please consider [a donation](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=4M7RMVNMKAXXQ&source=url).
