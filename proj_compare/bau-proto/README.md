# BAU

There are two cases contained in the folders `bau-proto` and `ze`.

## bau-proto (aka business-as-usual prototype reference)

This case considers the energy performance of a circa 2016 modular prototype in the Sacramento, CA, location. The model specifications are equivalent to the minimum design requirements.

* OpenStudio Standards: ASHRAE 90.1-2013 for 3B climate zone.
  * Envelope
  * Heat pump COP
  * ERV efficiencies
  * Appliance loads???

## worklow file gives model parameters

* ResidentialHotWaterHeaterTank
  * Skipped?: False
  * Fuel type: Natural Gas
  * Tank Energy Input Capacity: 40 kBtu/hr
  * Energy Factor (EF): 0.59
  * Location: auto-locate based on building type and occupancy type
  * Setpoint temperature: 125 F
  * Tank Volume: 50 gallons
  
* zero_energy_multifamily
  * Skipped?: False
  * Add Constructions?: True
  * Add Elevators?: True
  * Add Exterior Lights: True
  * Add HVAC?: True
  * Add Space Type Loads?: True
  * Add Service Water Heating?: True
  * Add Thermostats?: True
  * HVAC System Type: Minisplit Heat Pumps with ERVs
  * On-site parking fraction: 0%
  * Wall/Roof Construction Template: Better
    * must see `measures/zero_energy_multifamily/resources` for values
  * Window Construction Template: Better
    * must see `measures/zero_energy_multifamily/resources` for values


