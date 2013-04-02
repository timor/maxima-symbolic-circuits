maxima-symbolic-circuits
========================

solving electronic circuits symbolically in maxima CAS

How it works
============
circuit description is entered as a series of relations between nodes in a circuit, e.g.

    impedance(1,3,R);


defines a resistance R between the ground node (always node 1) and node 3.

After all elements have been specified, `solve_circuit();` gives the solution of all node voltages e,
branch voltage drops v and branch currents i.

The solution set can then be used to calculate transfer functions, or replace parts of the circuits with equations
(e.g. dependent sources), and use maxima's integrated solver for further calculations

Limitations
===========
- currently, number of nodes and branches must be known beforehand, and entered with `reset_circuit(n,b)`, respecitvely
- if solver fails, that indicates a malformed circuit, but no hints are given (check the system of equations with sparse_eq(); )
- sources with parallel impedances must be modeled with a pseudo-branch of R=0 at the moment
