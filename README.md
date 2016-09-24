This script was used to simulate nuclear quadrupole resonance (NQR) spectra using hybrid quantum spin register. Here a single electronic spin qubit is used as a sensor while a proximal nuclear spin is used as the target. Both the electronic and nuclear spins can be of arbitrary sizes, but the most interesting cases are when the nuclear spin is quadrupolar (I > 1/2). We assume that an XY8 dynamical decoupling sequence is applied to the electronic spin qubit. This code was used to simulate spectra presented in Lovchinsky et al., Science, 351, 836 (2016), Figure 4. Specifically, we considered the case of the nitrogen-vacancy (NV) color center in diamond (S = 1) interacting with nuclear spins in organic molecules chemically attached to the proximal diamond surface.

In order to run the code, follow these steps:

	1). Update the file 'parameters.txt' with the desired spectrum parameters. 
		The required parameters are:

		spin_e: the quantum number of the electronic spin
		spin_n: the quantum number of the nuclear spin
		Egyro: gyromagnetic ratio of the electronic spin [Hz/G]
		Ngyro: angle of principal axis of electronic spin [radians]  
		Bfieldx: applied magnetic field, x-component [G]
		Bfieldy: applied magnetic field, y-component [G]
		Bfieldz: applied magnetic field, z-component [G]
		NV_ZFS: zero-field splitting of electronic spin [Hz]
		Q: nuclear quadrupole coupling constant [Hz]
		eta: nuclear asymmetry parameter
		dispx: displacement of electronic and nuclear spins, x-component [nm]
		dispy: displacement of electronic and nuclear spins, y-component [nm]
		dispz: displacement of electronic and nuclear spins, z-component [nm]
		Npi: number of applied pi-pulses on electronic spin
		tau_min: minimum pi-pulse spacing [s]
		tau_max: maximum pi-pulse spacing [s]
		numpoints: number of time points in the spectrum

		The function 'initializeParameters' reads these values into a Python dictionary. 

	2). You also need to make sure the necessary constants are included in the file 'constants.txt'. 
		The required constants are:

		hbar: reduced Planck?s constant [m^2 kg s^-1]
		mu_B: Bohr magneton [J T^-1]
		u_0: permeability of free space [T m A^-1]
		
		The function 'initializeConstants' reads these values into a Python dictionary. 

	3). Open the ipython notebook 'SimulateSpectrum.ipynb'. Scroll to the bottom, past the class 
		and function definitions. Modify the block of code denoted by 'MODIFY THIS BLOCK' by 
		creating a custom Hamiltonian object.

	4). Run the notebook to generate spectrum. The final block of code plots some example spectra.

	5). The result of the simulation is written to the text file 'spectrum_output.txt'.