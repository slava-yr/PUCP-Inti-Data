# Photovoltaic Technologies Characterization and Ambient Parameters Dataset

This dataset provides outdoor measurements of photovoltaic (PV) modules representing multiple commercial PV technologies, along with synchronized environmental and operational parameters. The dataset is intended to support AI model training, benchmarking, and validation for power and energy system applications, including PV modeling, performance prediction, fault detection and maximum power point tracking (MPPT).

The dataset accompanies a data description report and a brief introduction document, which provide detailed background, data processing methodologies, validation procedures, and example AI use cases.


## Dataset Overview
- Time span: 2022–2025  
- Location: Outdoor Solar Laboratory, Pontificia Universidad Católica del Perú, Lima, Peru  
  (12°04′ S, 77°04′ W)  
- Scale: Over 1.7 million records  
- PV technologies: Thin-film, PERC, HIT, HJT, TOPCon  
- Data format: CSV  
- Time reference: Local time (UTC-05:00, no daylight saving time)

Measurements were collected under real outdoor operating conditions, including varying irradiance, temperature, and weather states.

## File Description

The dataset consists of two CSV files:
### 1. 'PV_dataset.csv'
This file contains time-resolved electrical and environmental measurements associated with individual PV modules.

#### Metadata: 
* module_name: Identifier of the PV module.  
* timestamp: Measurement time in format `YYYY-MM-DD HH:MM:SS` (local time, UTC-05:00).

#### Electrical variables:
* Vmpp: Voltage at the maximum power point [V].
* Impp: Current at the maximum power point [A].
* Pmpp: Power at the maximum power point [W].
* Isc: Short-circuit current, extrapolated from the I–V curve [A].
* R2_Isc: Coefficient of determination of the linear fit used for Isc extrapolation.
* Voc: Open-circuit voltage, extrapolated from the I–V curve [V].
* R2_Voc: Coefficient of determination of the linear fit used for Voc extrapolation.
* Rsh: Shunt resistance, computed from I–V curve analysis [Ohm].
* Rs: Series resistance, computed from I–V curve analysis [Ohm].
* FF: Fill Factor [%].
* V_ini: Initial voltage of the traced curve [V].
* I_ini: Initial current of the traced curve [A].

*Note:* Computed variables are derived per curve tracing. Detailed processing methods and assumptions are documented in the accompanying data report.

#### Environmental variables:
* G_spec_int: Irradiance computed via spectral irradiance integration [W/m²]. 
* G_tilt20_start / end: Measured irradiance tilted 20 degrees at curve start / end [W/m²].
* G_tilt15_start / end: Measured irradiance tilted 15 degrees at curve start / end [W/m²].
* G_horiz_start / end : Measured horizontal irradiance at curve start / end [W/m²].
* G_east_start / end: Measured vertical irradiance facing east at curve start / end [W/m²].
* G_west_start / end: Measured vertical irradiance facing west at curve start / end [W/m²].
* G_refl_start / end: Measured reflected irradiance at curve start / end [W/m²].
* module_temperature_center: Measured temperature at the center of the module [°C].
* module_temperature_lateral: Measured lateral temperature of the corresponding module [°C].
* air_temperature: Measured ambient air temperature [°C]. 
* relative_humidity: Measured relative humidity [%].
* air_density: Measured air density [kg/m^3].
* abs_pressure: Measured absolute air pressure [hPa].
* wind_speed_ms: Measured wind speed [m/s].
* wind_direction: Wind direction [°].

### 2. 'module_metadata.csv'
This file provides module-specific datasheet and installation information.

* module_name: Identifier of the corresponding PV module. Suffixes indicate installation configuration or setup:
  - `-T`, `-V`: Tilted or vertical mounting configuration.
  - `-f`: Bifacial module with the rear side covered (front-side operation only).
  - `-r`: Bifacial module mounted with the rear side facing upward and the back covered.
* commercial_name: Commercial model name.
* technology: PV technology type.
* bifacial: Bifacial module indicator (yes/no).
* bifaciality_factor: Bifaciality factor (0-1).
* area_m2: Module area [m²].
* installation_tilt: Installation tilt angle (15°, 20°, or 90° vertical, facing west).  
* Voc_stc: Open-Circuit Voltage at STC [V]. 
* Isc_stc: Short-Circuit Current at STC [A].
* Vmpp_stc: Voltage at Maximum Power Point at STC [V].
* Impp_stc: Current at Maximum Power Point at STC [A].
* Pmpp_stc: Maximum Power at STC [W].
* NOCT_c: Nominal Operating Cell Temperature [°C].
* temp_coeff_Isc_pct: Temperature coefficient of Isc [%/°C].
* temp_coeff_Voc_pct: Temperature coefficient of Voc [%/°C].
* temp_coeff_Pmpp_pct: Temperature coefficient of Pmax [%/°C].
* datasheet_url: URL to datasheet.

## Data Processing, Quality, and Reproducibility

- Electrical parameters labeled as computed are derived from measured I–V curves.  
- Quality indicators (R² values) are provided to support filtering and reliability assessment.  
- Detailed preprocessing, curve fitting, validation procedures, and uncertainty considerations are described in the accompanying data description report.  
- Data processing scripts and notebooks are provided separately to ensure reproducibility.

## Intended Use

This dataset is suitable for:
- AI-based PV performance modeling  
- MPPT algorithm development and benchmarking  
- PV technology comparison under real outdoor conditions  
- Data-driven power electronics and renewable energy research

The dataset does contain personally identifiable information (PII) or sensitive critical infrastructure data.

## License

This dataset is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

The data were collected within the MatER Research Group at the Pontificia Universidad Católica del Perú (PUCP). Users are free to share and adapt the data for any purpose, including research and commercial use, provided appropriate credit is given to the original authors and source.


