# Eceff
Matlab script to calculate the effective critical field for runaway generation in the presence of partially ionized impurities, according to equation (26) in Hesslow et al, Submitted to PPCF (2018), arXiv:1802.00717 [physics.plasm-ph]. 

The plasma composition can be any any fully ionized species in combination with partially ionized neon and/or argon

INPUT:
	
	Z   : atomic number of each ion species
    Z0  : net charge of plasma for each ion species
    nj  : density of each ion species [m^(-3)]
    Z, Z0 and nj must be vectors of length nSpecies
    T   :  temperature [eV]  (for calculation of the Coulomb logarithm)
    B   : magnetic field [T]
	
OUTPUT:
    
	Eceff/Ectot, where Ectot = (ntot / ne) E_c = ntot e^3 lnLStar/(4 pi epsilon_0^2 m_e c^2)
	
USAGE: 

For a plasma with a density of 10^20 m^(-3) deuterium and 10^20 m^(-3) Ar+, a temperature of 10 eV and B = 2 T
	
	Z = [1; 18];
	Z0 = [1; 1];
	nj = 1e20*[1;1];
	T = 10;
	B = 2;
	EceffOverEctot = calculate_Eceff(Z, Z0, nj, T, B);
