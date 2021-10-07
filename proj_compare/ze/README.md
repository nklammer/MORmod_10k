# Two Cases

There are two cases contained in the folders `bau-proto` and `ze`.
  
## ze (aka zero energy)

* OpenStudio Standards: Multifamily ZE

### workflow file gives model parameters

* ResidentialHotWaterHeaterHeatPump
  * Skipped?: False

* zero_energy_multifamily
  * Skipped?: False
  * Add Constructions?: True
  * Add Elevators?: True
  * Add Exterior Lights?: True
  * Add HVAC?: True
  * Add Space Type Loads?: True
  * Add Service Water Heating?: True
  * HVAC System Type: Minisplit Heat Pumps with ERVs
  * On-site parking fraction: 0%
  * Wall/Roof Construction Template: ZE AEDG Multifamily Recommendations
    * Must see `measures/zero_energy_multifamily/resources` for values
  * Window Construction Template: ZE AEDG Multifamily Recommendations
    * Must see `measures/zero_energy_multifamily/resources` for values
