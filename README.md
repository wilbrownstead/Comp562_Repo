Code Repository for the final project submission of William Brownstead, Grayson Clark, Alyssa Zhao, and Connor Hall for UNC's COMP562 class.

Also featured is the PDF of the final report and a copy of our extra credit presentation slides. 

For the K-NN_test file, only the first box of code is necessary to run to see the results featured in the project report. Uploaded in this repository is a csv file containing 20,000 instances as a demonstration set. 
Each exoplanet has values for the following feature column names:   

PlanetIndex	star_class	star_temperature_in_Kelvin	star_radius_in_Solar_radii	distance_from_Earth_to_the_system_in_parsecs	semimajor_axis_of_the_planet_in_AU	planet_radius_in_km	planet_density	planet_surface_pressure_bars    

kappa	gamma1	gamma2	alpha	beta planet_surface_temperature_Kelvin	  

H2O	CO2	O2	N2	CH4	N2O	CO	O3	SO2	NH3	C2H6	NO2	  

planet_atmospheres_avg_mol_wgt	planets_mean_surface_albedo.  



***K-NN Test Code and Usage***

In order to execute the K-NN_test code, download this file (9.5 MB) and change the line: 
```df = pd.read_csv('/Users/William/562Project/combined_models.csv')``` 
to your local path.



***Datasets for CNN***

Both partial datasets provided can be found in the link below. Please read through this section before downloading any data.
- https://gofile.io/d/CM3QPs

An .npy file containing 30 thousand spectra files (~1.8GB)
- It is recommended that you use this file for running the CNN as a demo. This small of a dataset will not yield good results, but it does not take up a ton of storage and can be handled relatively quickly by the model.

A second .npy file containing 121,000 spectra files (~7.4GB)
- The corresponding PSG models .csv file must be downloaded as well (~63mb)
- This is only recommended for use if you have plenty of storage on your computer and a lot of time on your hands. This data set will still not yield great results, but it will be a massive step up from the previous two.
- Expect each full run of the model to take at least 15 minutes per gas, but could take much longer depending on the build and age of your computer.

Unfortunately, supplying the full 300,000 spectra dataset is impossible due to the fact that it is over 180GB. If you would like to download a larger dataset for yourself, you can find the full 3.1 million planet dataset here: https://exoplanetarchive.ipac.caltech.edu/cgi-bin/FDL/nph-fdl?psg. Instructions and scripts for downloading the dataset can be found here: https://exoplanetarchive.ipac.caltech.edu/cgi-bin/FDL/nph-fdl?psg.



***Steps for running the CNN***

1. Upon downloading the dataset of your choosing, simply place the files into the data/ directory, or store it locally on your computer.
2. Ensure that the spectra data is in .npy format, and the PSG model data is a .csv.
3. Within the model, update these lines of code with the correct paths to where the data is located on your computer:

   - If stored in the data/ directory:
       - ```spectra_data = np.load("..\\Data\\{spectra_data_file_name.npy")```
       - ```metadata = pd.read_csv("..\\Data\\{PSG_models_file_name}.csv")```
   - If stored locally, replace both strings above with the full paths to where the data is stored on your computer.
       - For example: ```spectra_data = np.load("G:\\Comp 562 Exoplanet Data Raw per 10000\\npy_outputs\\ALL_planet_spectra_combined.npy")```

4. After doing this, and installing all dependencies (requirements.txt coming soon), the model should be fully good to go.

***DISCLAIMER: This model is intended to be run on a computer with an independent GPU as it utilizes PyTorch's GradScaler() and autocast for computing speed. If your system does not have a GPU, you will have to remove these features for the model to run properly. This task is relatively straightforward, but if you cannot figure out how to do it and need a version that only utilizes the CPU, email me at connorbh@ad.unc.edu and I can provide that for you.***

***Training this model is not fast. Due to the complexity and large number of trainable parameters that this CNN utilizes, even on a high-end GPU, this model can take upwards of 90 minutes to train a 300k planet data set on a singular gas. Without access to a GPU, this could take anywhere from 30x to 100x longer (rough estimate). For this reason, it is not recommended to use large datasets unless you are sure your system can handle it.***

