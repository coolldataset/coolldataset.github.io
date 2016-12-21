---------------------------------------------------------------------------------------------------
Contents of the COOLL (folder):
---------------------------------------------------------------------------------------------------
1) Configs (.zip file)
2) Data (folder)
3) Headers (.zip file)
4) appliances_and_action_delays.txt
5) README.txt
6) scaleFactors.txt
---------------------------------------------------------------------------------------------------
Contents details:
---------------------------------------------------------------------------------------------------
1) Configs (.zip file):

Contains 840 ".txt" files (scenario1_1.txt to scenario1_840.txt). These files contain details about the measurement configuration and scenario (chosen outlets on measurement system and measured appliances, pre-trigger duration, action delays, ...).

File name convention:
	scenario[number_of_measured_appliances]_[measurement_id].txt

	- number_of_measured_appliances: an integer number from 1 to 6 (for COOLL it is always 1)
	- measurement_id: an integer number from 1 to 840 representing the measurement identification number
---------------------------------------------------------------------------------------------------	
2) Data (folder):

Contains 1680 ".flac" files (scenarioC1_1.flac to scenarioC1_840.flac and scenarioV1_1.flac to scenarioV1_840.flac) representing current and voltage measurements coded using the "free lossless audio codec (flac)" format. To avoid very large file size downloads, the files are put in 8 different ".zip" files (4 for current and 4 for voltage) of around 220 MB each.

File name convention:
	scenario[measurement_type][number_of_measured_appliances]_[measurement_id].flac

	- measurement_type: either "C" for current or "V" for voltage
	- number_of_measured_appliances: an integer number from 1 to 6 (for COOLL it is always 1)
	- measurement_id: an integer number from 1 to 840 representing the measurement identification number

IMPORTANT: the amplitude of the data contained in these files is scaled to range between -1 and 1 (a constraint due to the coding process). The user must use the "scaleFactors.txt" file to recover the real amplitude of the data (see section 6).
---------------------------------------------------------------------------------------------------
3) Headers (.zip file):

Contains 42 ".xlsx" files containing informations about the 42 measured appliances (type, nominal power, ...)
---------------------------------------------------------------------------------------------------
4) appliances_and_action_delays.txt:

This file gives the measured appliance names and corresponding action delay of each measurement instance in the form: [measurement_id]: [appliance_name_and_id]_[action_delay]ms

These informations may be retreived from the configuration files (see section 1 about the Configs folder) 
---------------------------------------------------------------------------------------------------
5) README.txt: 

The present file describing the contents of the COOLL folder.
---------------------------------------------------------------------------------------------------
6) scaleFactors.txt:

A file containing current and voltage scaling factors that allow the user to recover the real amplitude of all 840 measurement instances. The first column represent the current scaling factors and the second one the voltage scaling factors. The line number (from 1 to 840) represent the measurement id. After scaling, the current amplitude is in "Amps" and the voltage amplitude in "Volts".
---------------------------------------------------------------------------------------------------