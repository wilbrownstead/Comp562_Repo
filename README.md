Code Repository for the final project submission of William Brownstead, Grayson Clark, Alyssa Zhao, and Connor Hall for UNC's COMP562 class.

Also featured is the PDF of the final report and a copy of our extra credit presentation slides. 

For the K-NN_test file, only the first box of code is necessary to run to see the results featured in the project report. Uploaded in this repository is a csv file containing 20,000 instances as a demonstration set. 
Each exoplanet has values for the following feature column names:   

PlanetIndex	star_class	star_temperature_in_Kelvin	star_radius_in_Solar_radii	distance_from_Earth_to_the_system_in_parsecs	semimajor_axis_of_the_planet_in_AU	planet_radius_in_km	planet_density	planet_surface_pressure_bars    

kappa	gamma1	gamma2	alpha	beta planet_surface_temperature_Kelvin	  

H2O	CO2	O2	N2	CH4	N2O	CO	O3	SO2	NH3	C2H6	NO2	  

planet_atmospheres_avg_mol_wgt	planets_mean_surface_albedo.  


In order to execute the K-NN_test code, download this file (9.5 MB) and change the line: 
```df = pd.read_csv('/Users/William/562Project/combined_models.csv')``` 
to your local path.

A .npy file containing 10 thousand spectra files can be downloaded at: https://gofile.io/d/IzQGtI
It is 3.1 GB and will not yield good results when used to train/test the CNN, but it is meant as a demo. A large enough dataset to yield results consistent with our project is too large and would take to much time to expect a grader to be able to run.
