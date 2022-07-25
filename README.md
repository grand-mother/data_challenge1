# Data Challenge 1


## The **Main Objective** of the Data Challenges:

Prepare the full simulation and data analysis chain for UHECR/UHEnu.


## **Specific Objectives** of the data challenge:

* Tune & validate the ROOT data format, ZHAireS to ROOT conversion
* Add ROOT input/output to the electronic chain
* Identify what is missing in GRANDlib
* Document the simulation and data analysis chain and the interfaces

As the code you will produce during the data challenge may be included in the grandlib, it is highly recommanded that the code writing standard of grandlib are followed. These are presented here [].


## Rules of the game:
* You may pick any Data Challenge you like (all of them is posible)
* You may work alone or in teams
* Each team produces in principle an independent code, but communication among teams and code sharing is encouraged
* Progress will be discussed during soft meetings and through direct exchanges (for example, on GitHub)
* Tentative deadline for DC1 is early September, and the next GRAND meeting for DC2 (Nijmegen, late October / early November or early January). 
* After the DCs are completed, the various codes will be evaluated and we will work towards the unification of the production of a standard / official GRANDlib code
* Parameters for code evaluation will be:
    * Validity of the results produced
        * Eg. for DC1: can the initial Efield be indeed retrieved by antenna response deconvolution? 
        * Eg. for DC2: how well the true parameters of the showers are reproduced?
    * Codes speed and memory usage
    * Modularity, easiness of use and possibility for evolution
    * Compliance with GRANDlib coding standards


## Data Challenge 1

***Produce ADC traces from ROOT files with Efield.***

**Objectives:**

* Use the same antenna response; files: [EW](https://github.com/grand-mother/store/releases/download/101/GP300Antenna_Ewarm_leff.npy)
[SN](https://github.com/grand-mother/store/releases/download/101/GP300Antenna_Snarm_leff.npy)
[Z](https://github.com/grand-mother/store/releases/download/101/GP300Antenna_Zarm_leff.npy)
* Use the same electronics response; [script for direct ZHAireS output](https://github.com/grand-mother/grand/blob/dev/scripts/grand_simu_trace2du.py) (needs to be made to read ROOT files)
* Use the same noise model; [script for direct ZHAireS output](https://github.com/grand-mother/grand/blob/dev/scripts/grand_simu_trace2du.py) (needs to be made to read ROOT files)
* All three need to be plugable (inputs to the routine, or a config file?)
* Use the GRANDlib ROOT TTrees interface (to be documented, but reading/writing examples are [here](https://github.com/grand-mother/grand/tree/dev_io_root/examples/io))

**Inputs:**

- an antenna response file
- an electronics response module
- Efield [traces](https://github.com/grand-mother/data_challenge1/tree/main/coarse_subei_traces_root) at the antenna feed point in the ROOT format

**condition:** add the noise in a plugable way

**Output:**	Two ROOT files, created using GRANDlib ROOT interfaces, containing clean and noisy ADC traces


## Pre-Data Challenge:
***Validate full production of simulated traces in the ROOT format.***

* Use the [ZHAireSInputGenerator.py](https://github.com/grand-mother/data_challenge1/blob/main/ZHAireSInputGenerator.py) to generate input
* Use [ZHAireS](https://github.com/mjtueros/ZHAireS-Python) to generate traces from the input
* Use [ZHAireSRawToGRANDROOT.py](https://github.com/grand-mother/grand/blob/dev_io_root/examples/io/ZHAireSRawToGRANDROOT.py) to convert traces to the ROOT format (this is in dev_io_root branch, not the master yet)

## Deadline

Somewhere in early September 2022.

## Discussion

* For specific bugs/issues, please use this repository's Issues function.
* For more general discussion, please use (SLACK or Github discussion?)
* For ROOT format and GRANDlib interfaces to it ask Lech Piotrowski
* For ZHAireS ask Matias Tueros

**A remark:** Not all tools and interfaces are ready and Data Challenges are a way to prompt their          creation, validation and testing. Thus a close cooperation between the participants and the author of parts of the functionality (for example, Lech for ROOT interfaces) is a must.

Data Challenge 2, focused on EAS reconstruction will follow after the Data Challenge 1 is concluded.



