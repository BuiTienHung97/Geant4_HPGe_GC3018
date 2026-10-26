
		     ==========================================================================================
						    Geant4 - GAMMAKNIFE ART-6000 TM
		     ==========================================================================================

							   README file
				          --------------------------------------------
		 					   B. T. Hung

						Hanoi University of Science and Technology
						      hungbuitien19081997@gmail.com
					
		 -------------------------------------------------------------------------------------------------


I. INTRODUCTION
 This simulation was performed to calculate the dose profies in water phantom from Rotating Gamma Knife ART-6000 TM.
 The Gamma ART 6000 TM has 30 Cobalt sources that focused on to center of sphere phantom with 8 cm radius.
 The colliamtor system have 2 parts included primary collimator and secondary collimator.
                                                 
                                                                      
II. Files and folders
 GammaART6000TM
 |----- ART-6000TM(Ver1.0)[dir]
 	|
 	|----- include [dir]
 	|	|
	|	|----- MyActionInitialization.hh
	|	|
	|	|----- MyDetectorConstruction.hh
	|	|
	|	|----- MyPhysicList.hh
	|	|
	|	|----- MyPrimaryGenerator.hh
	|
 	|----- src [dir]
 	|	|
	|	|----- MyActionInitialization.cc
	|	|
	|	|----- MyDetectorConstruction.cc
	|	|
	|	|----- MyPhysicList.cc
	|	|
	|	|----- MyPrimaryGenerator.cc
	|
 	|----- CMakeLists.txt
	|
	|----- defaultMacro.mac
 	|
 	|----- GPS.in
 	|
 	|----- MySimulation.cc
 	|
 	|----- simulation.mac


III. How to run



IV. Explain	 

a) ART-6000TM(Ver1.0) - Deposited dose in water phantom with single source

	---->  Primary Generator.

	To create the original gamma rays emmitted from the activate cobalt source, we used General Particle Source (GPS) method. All source information were defined in the GPS.in macro file.
	The primary particle beam parameter are:
		- energy of gamma: 1.17 and 1.33 MeV with the same probability 
		- X Y Z positions sampled in a cylinder 29 mm lenght and 1.35 mm of radius
		- angular biasing within an angle of 3 degree: it has been checked not to influence final results (respect to a 4p isotropic sampling) drastically decreasing computatuin time


	----> Geometrical Set-Up.
 
 
	----> Physics

	Method: Modular Physics List 
	Used the G4EmStandardPhysics_option3 - for medical and space science applications


	----> Scoring

	Method: Built-in Scoring commands                                
	At the end of the simulation the energy deposited in each voxel of the scoring mesh inside the spherical phantom is registered in the eDep_scorer.out file. 
	Default voxelization is 45 x 45 x 45 cubic voxels 1 mm of side. 

---------------------------------------------------------------------------


For comments, advices and questions please contact: 
hungbuitien19081997@gmail.com

02/13/2022 - Released Ver 1.0 with some features:
		+ 
