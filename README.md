# Self-Adaptive-Circuits

This repo contains the implementation of a self-adaptive differential amplifier which is immune to change in temperature and noise in the supply voltage. 

## Block Diagram
![image](https://github.com/JeyKeyWrma/Self-Adaptive-Circuits/assets/99319804/07b38049-518e-4150-baaf-361f9eb32a70)

## Implementation
The circuit of our interest the differential amplifier which we simulated in [MicroCap](https://micro-cap.informer.com/12.0/) as an alternative to LTSpice/NGSpice as it has more flexibilty in various analysis of our ciruit. Data for VDD changing from 10V to 14V with a step of 0.1V and temperature varying from 20 to 80 degrees Celsius were collected from this simulation. Now this data was used to train and test an ML model such that it predicts the output of our circuit for a certain temperature and VDD. Using the weights and biases of the model we designed an equation which takes temperature and VDD as input and gives us the desired output. After realising the same circuit in hardware we connect an arduino and fed the aforementioned equation to arduino such that arduino senses the temperature(using BMP280) and the VDD using a simple voltage divider and prints out the parameter that needs to be changed for the ciruit to behave an room temperature and ideal VDD.
Video link for [working](https://iiitaphyd-my.sharepoint.com/:v:/g/personal/jampana_varma_research_iiit_ac_in/Ef-_5KQI8cBCnni4c2mKFqIBfrzSuu50ntmASUeO7L3oBA?e=kpyeh6https://iiitaphyd-my.sharepoint.com/:v:/g/personal/jampana_varma_research_iiit_ac_in/Ef-_5KQI8cBCnni4c2mKFqIBfrzSuu50ntmASUeO7L3oBA?e=kpyeh6) of the circuit and video link for the [presentation](https://iiitaphyd-my.sharepoint.com/:v:/g/personal/jampana_varma_research_iiit_ac_in/EeFJnxp_LBBPqry9RLIxjygBzmHgjGTutIkJa1In4_B2mA?e=uOcGpS) of the project.
