---
layout: post
title: Predicting Mechanical Properties of Polymers with ReaxFF
---

Molecular dynamics (MD) modeling is a powerful, efficient, and cost-effective tool for designing new composite materials. MD modeling simulates systems of molecules according to physics models called force fields which describe the interactions between atoms. This post will describe the general process for predicting the mechanical properties of polymers with the reactive force field, ReaxFF. NOTE: This post is intended as a general guide and not a step-by-step tutorial. 

The first step in the process is building your monomers. The first force field you will use in this process is called OPLS and it is a fixed bond force field. A molecule in OPLS is defined as a collection of atoms in 3D space with a certain number of bonds, angles, and dihedrals. Each bond, angle, and dihedral must be explicitly written down in the molecule file. Building your monomer can take a good bit of time. A good way to build it is by drawing the molecular structure on paper, numbering the atoms, and then making a list of each bond, angle, and dihedral. There may be tools that automate the process, but manually building the monomer is a good exercise (and must only be done once). For most epoxies you will have two monomers: the epoxy monomer and the hardener monomer. Also, don't forget to look up the necessary OPLS AA (all atom) parameters to include in the .mol file.

The second step in the process is simulating your monomer to make sure it was constructed correctly. [LAMMPS](http://lammps.sandia.gov/) is an excellent MD code and most of us use it. 

