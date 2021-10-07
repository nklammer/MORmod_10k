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
      {
         "arguments" : 
         {
            "__SKIP__" : false,
            "fuel_type": "gas",
            "capacity": "40.0",
            "energy_factor": "0.59",
            "location": "auto",
            "setpoint_temp": "125",
            "tank_volume": "50"
         },
         "measure_dir_name" : "ResidentialHotWaterHeaterTank",
         "name" : "ResidentialHotWaterHeaterTank"
      },
         {
            "__SKIP__" : false,
            "add_constructions" : true,
            "add_elevators" : true,
            "add_exterior_lights" : true,
            "add_hvac" : true,
            "add_space_type_loads" : true,
            "add_swh" : false,
            "add_thermostat" : true,
            "hvac_system_type" : "Minisplit Heat Pumps with ERVs",
            "onsite_parking_fraction" : "0.0",
            "wall_roof_construction_template" : "Better",
            "window_construction_template" : "Better"
         },
         "measure_dir_name" : "zero_energy_multifamily",
         "name" : "zero_energy_multifamily"
      },


