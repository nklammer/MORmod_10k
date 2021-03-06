# 10k
This repository contains resources and documentation for the building energy modeling portion of the methods of the FY 22 "10k" technical report (TP-5500-81037). The workflow is forked and edited from Noah Klammer's 2021 MS thesis in the repo `MORmod_mf`. The work was inspired by and heavily borrows from previous work done for the publication of the Zero Energy Design Guide for Multifamily buildings. A [related publication](https://www.nrel.gov/docs/fy20osti/77013.pdf) detailing the technical work is available for free.


# Versions
* Ruby 2.5.5p157 ([download](https://rubyinstaller.org/downloads/archives/))
* OpenStudio 3.0.1 ([download](https://github.com/NREL/OpenStudio/releases/tag/v3.0.1))
  * EnergyPlus 9.3.0 (included in the above)
  * approximately resstock-2.2.0 ([download](https://github.com/NREL/resstock/releases/tag/v2.2.0))
* Git Bash for Windows (a git-enabled shell) v2.30.0(2) ([download](https://github.com/git-for-windows/git/releases/tag/v2.30.0-rc2))


# Ruby Gems
This project counts on many local changes to published packages (or in Ruby parlance "gems"). For that reason it is suggested to rely on local resources inside this repository instead of external public gems.

Many of the Measures are clones or derivatives of residential energy modeling code from the NREL `resstock` [repository](https://github.com/NREL/resstock). Learn more about ResStock [project](https://resstock.nrel.gov/) and [Residential Energy Modeling](https://www.nrel.gov/buildings/residential.html).

### [openstudio-standards gem](https://github.com/NREL/openstudio-standards)
This workflow uses OpenStudio v3.0.1 which has `openstudio-standards-0.2.11` embedded. If one desires to access building performance standards ASHRAE `90.1-2016` or `90.1-2019`, a more recent `openstudio-standards-0.2.XX` will be required available from [rubygems.org](https://rubygems.org/gems/openstudio-standards).

Due to a bug in OpenStudio Command Line Interface, the GEM_PATH path variable needs to be taken out of the environment before running.
In Git Bash shell command for Windows `$ unset GEM_PATH` and check for presence with bash line `$ env | grep GEM`.

### [resstock gem](https://github.com/NREL/resstock)

# EMS
## Heat Pump Water Heater
This specific workflow has an implementation of a heat pump water heater that requires some EnergyPlus Energy Management System (EMS) code. Be aware that in order for the EMS code to run, certain output variables are "baked in" to the model reporting variables and should not be changed or replaced. The EMS argument mapping changed in > EnergyPlus v9.3.0 and so users may see the `EnergyManagementSystem:ProgramCallingManager` error.

# Viewing Results

I recommend using the free software, ResultsViewer to view and export `eplusout.eso` files to `.csv` format for analysis. From my experience, there is no limit on the number of variables for ResultsViewer to work. Be aware that the parsing of `eplusout.eso` files gets exponentially slower with more reporting variables, especially at time interval (t <= 1 hour).

I have also found the Python [`esoreader`](https://github.com/architecture-building-systems/esoreader) project useful in a Python environment.

Standalone releases of EnergyPlus include an executable file `ReadVarsESO.exe` which will take the `eplusout.eso` file and read it to a `.csv` format for a spreadsheet tool like Microsoft Excel. Beware that the limit on the number of variables is 255 because of Microsoft Excel limits but this limit can be overridden by specifying the `unlimited` option. Instructions [here](https://bigladdersoftware.com/epx/docs/8-0/input-output-reference/page-090.html).

I like the measure `d_view_export` measure that takes report variables in the `eplusout.sql` database file and writes them to a `.csv` file with the DView formatting. The DView  format adds a header to the raw data (see example in `../tips_dview-data-file-template.pdf`) so the DView data viewer ([download](https://github.com/NREL/wex/releases/tag/v1.2.0)) can view it. Be warned that this pathway is also limited to < 200 variables but has more to do with the character limits of the variable names so beware of long output variable names.

# Command Line Tips
Always run OpenStudio with Git Bash command `openstudio --verbose run -w path/to/workflow.osw --debug -- measures_only[optional]`. Do not exclude the `run.log` file and `eplusout.rdd` file in the commits.

# EnergyPlus Tips
If a reporting variable requested in the `in.osm` and `in.idf` files is not a valid EnergyPlus request, the simulation will still run successfully and return `true`. Therefore, it is important that after the simulation has finished, to check the `eplusout.mtd` meta-parameter file and to check the `eplusout.err` messages.


