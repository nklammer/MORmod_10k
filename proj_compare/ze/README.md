# Two Cases

There are two cases contained in the folders `bau-proto` and `ze`.
  
## ze (aka zero energy)

* OpenStudio Standards: Multifamily ZE

### workflow file gives model parameters
      {
         "arguments" : 
         {
            "__SKIP__" : false
         },
         "measure_dir_name" : "ResidentialHotWaterHeaterHeatPump",
         "name" : "ResidentialHotWaterHeaterHeatPump"
      },
         {
            "__SKIP__" : false,
            "add_constructions" : true,
            "add_elevators" : true,
            "add_exterior_lights" : true,
            "add_hvac" : true,
            "add_space_type_loads" : true,
            "add_swh" : true,
            "add_thermostat" : true,
            "hvac_system_type" : "Minisplit Heat Pumps with ERVs",
            "onsite_parking_fraction" : "0.0",
            "wall_roof_construction_template" : "ZE AEDG Multifamily Recommendations",
            "window_construction_template" : "ZE AEDG Multifamily Recommendations"
         },
         "measure_dir_name" : "zero_energy_multifamily",
         "name" : "zero_energy_multifamily"
      },
