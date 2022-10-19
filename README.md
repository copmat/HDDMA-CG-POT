# HDDMA-CG-POT
The coarse grained force field developed for the HDDMA radical polymerization

In this repository, we report the coarse grained force fields described in the article entitled:    
"Simulating Polymerisation by Boltzmann Inversion Force Field Approach and Dynamical Non-equilibrium Reactive Molecular Dynamics."     
Authors:     
Michele Monteferrante, Sauro Succi, Dario Pisignano, and Marco Lauricella     
corresponding author: Marco Lauricella - lauricella.marco@gmail.com      
      
In the following atom list A label stands for the lateral part of the HDDMA molecule 
from the methylidene group up to the oxygen of the ether group for a total of 85 Dalton.
In the following atom list B label stands for the central part of the HDDMA molecule 
containing six methylene groups for a total of 84 Dalton.     
Atom list:       
The atom 1 stands for the coarsed atom labelled A.    
The atom 2 stands for the coarsed atom labelled B.     
The atom 3 stands for the radical state of the coarsed atom labelled A.      
The atom 4 stands for the coarsed atom labelled A after the radical addition.       
The atom 5 stands for the coarsed atom labelled A after the termination reaction.       

The files could be used within the LAMMPS code by setting in the input file the commands    

The non-bonded interactions:     
pair_style table spline 1000       
pair_coeff 1 2 Bond-2.pot.fit Bond-2.new.fit 25.0   
pair_coeff 1 1 Bond-3.pot.fit Bond-3.new.fit 25.0    
pair_coeff 2 2 Bond-4.pot.fit Bond-4.new.fit 25.0   

pair_coeff 2 3 Bond-2.pot.fit Bond-2.new.fit 25.0   
pair_coeff 3 3 Bond-3.pot.fit Bond-3.new.fit 25.0   
pair_coeff 1 3 Bond-3.pot.fit Bond-3.new.fit 25.0   

pair_coeff 1 4 Bond-3.pot.fit Bond-3.new.fit 25.0   
pair_coeff 2 4 Bond-2.pot.fit Bond-2.new.fit 25.0   
pair_coeff 3 4 Bond-3.pot.fit Bond-3.new.fit 25.0   
pair_coeff 4 4 Bond-3.pot.fit Bond-3.new.fit 25.0   

pair_coeff 1 5  Bond-3.pot.fit Bond-3.new.fit 25.0    
pair_coeff 2 5  Bond-2.pot.fit Bond-2.new.fit 25.0   
pair_coeff 3 5  Bond-3.pot.fit Bond-3.new.fit 25.0   
pair_coeff 4 5  Bond-3.pot.fit Bond-3.new.fit 25.0   
pair_coeff 5 5  Bond-3.pot.fit Bond-3.new.fit 25.0   

The bonded interactions:   
bond_style hybrid harmonic table spline 400    
bond_coeff 1 table Bond-1.pot.fit Bond-1.new.fit     
bond_coeff 2 table Bond-5.pot.fit Bond-1-reacted.hist.fit   
bond_coeff 3 table Bond-6.pot.fit Bond-1-reacted.hist.fit     
bond_coeff 4 table Bond-7.pot.fit Bond-1-reacted.hist.fit     

angle_style table spline 400     
angle_coeff 1 Ang-1.pot.fit Ang-1.new.fit   
angle_coeff 2 Ang-2.pot.fit Ang-2-reacted.hist.fit   



