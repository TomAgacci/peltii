##############################################################################
#
# manual.md
#
# HSN THERMAL MASTER CONTROLLER
# POLAR TEC ENGINE
# HEAT / COOL / COLD-COLD CASCADE SYSTEM
#
##############################################################################

PROJECT
-------

HSN Thermal Master is a conceptual thermoelectric control framework using:

    • Peltier (TEC) modules
    • Polar control
    • Delta-T control
    • Bidirectional heat transfer
    • Single-stage operation
    • Multi-stage cascade operation
    • H-bridge polarity reversal
    • Current-regulated TEC control

The system is designed to allow:

    Heat  <========>  Cool

while independently controlling:

    Small Delta-T  <========>  Large Delta-T


##############################################################################
# REFERENCE TEC MODULE
##############################################################################

Same Sky CP60340

Physical Size

    30 mm x 30 mm x 4 mm

Electrical

    Rated Current (Imax)      6.0 A
    Rated Voltage (Vmax)      8.6 V
    Resistance                1.21 Ω

Thermal

    Cooling Capacity (Qmax)   29 W
    Maximum Delta-T           68°C

Manufacturer Temperature Limits

    Cold Side Limit           -40°C
    Hot Side Limit           +100°C

##############################################################################
# ABSOLUTE THEORETICAL TEMPERATURE RANGE
##############################################################################

This section represents the manufacturer's published limits.

Lowest Published Cold Side

    -40°C

Highest Published Hot Side

   +100°C

Maximum Published Spread

   140°C

Example

    Cold Side = -40°C

    Hot Side  = +100°C


##############################################################################
# HSN POLAR CONTROL RANGE
##############################################################################

Polar Control

    P = -1.0 to +1.0

Where

    -1.0 = Full Heat

     0.0 = Neutral

    +1.0 = Full Cool


Examples

P = +1

    Maximum Cooling

P = +0.5

    Moderate Cooling

P = 0

    Neutral

P = -0.5

    Moderate Heating

P = -1

    Maximum Heating


##############################################################################
# DELTA-T CONTROL RANGE
##############################################################################

Delta-T Control

    D = 0.0 to 1.0

Where

    0.0 = No Temperature Separation

    1.0 = Maximum Temperature Separation


Examples

D = 0

    Both sides near ambient

D = 0.5

    Moderate separation

D = 1.0

    Maximum separation


##############################################################################
# SINGLE TEC EXPECTED OPERATING RANGE
##############################################################################

Assuming:

    Ambient = 27°C

Typical Practical Cooling Range

    +27°C to approximately -10°C
    depending on load

Light-Load Cooling

    +27°C to approximately -25°C

Near-No-Load Cooling

    +27°C to approximately -40°C

Typical Hot Side Range

    +27°C to +70°C

Heavy Load Hot Side

    +70°C to +100°C

depending on heatsink performance.


##############################################################################
# TWO-STAGE CASCADE HSN EXAMPLE
##############################################################################

Model Assumptions

    2x CP60340 modules

    Heatsink held at 27°C

    Load = 2 W

Result

    Tc = -45.69°C

    Tm = +19.38°C

    Th = +27.00°C

Important

    This value exceeds the published
    -40°C module cold-side limit.

    Therefore:

        -45.69°C

    should be considered a MODEL RESULT,
    not a recommended operating temperature.


##############################################################################
# RECOMMENDED OPERATING LIMITS
##############################################################################

Safe Conservative Limits

Cold Side

    Target:

        -35°C

    Alarm:

        -38°C

    Shutdown:

        -40°C


Hot Side

    Target:

        < +60°C

    Alarm:

        +80°C

    Shutdown:

        +95°C


##############################################################################
# TEMPERATURE MODES
##############################################################################

MODE A
------

Maximum Cooling

    Polar  = +1.0
    DeltaT = 1.0

Example

    Cold = -35°C

    Hot  = +75°C


MODE B
------

Moderate Cooling

    Polar  = +0.5
    DeltaT = 1.0

Example

    Cold = -4°C

    Hot  = +51°C


MODE C
------

Compression Mode

Example

    Cold = +10°C

    Hot  = +40°C

Use:

    Potentiometer set between
    minimum and maximum Delta-T.


MODE D
------

Neutral

Example

    Cold = +27°C

    Hot  = +27°C

No active heat pumping.


MODE E
------

Heating

Polarity Reversed

Example

    Plate = +40°C

while opposite side cools.


##############################################################################
# CONTROL PANEL
##############################################################################

Dual Pot Version

Pot #1

    POLAR

    HEAT <=====> COOL

Pot #2

    DELTA-T

    LOW <=====> HIGH


Display

    Tc
    Th
    Current
    Voltage
    Power


##############################################################################
# ELECTRICAL REQUIREMENTS
##############################################################################

Single TEC

    12 VDC
    6 A

Recommended Supply

    12 V
    10 A minimum


Dual Cascade

    12 V
    15 A minimum

Recommended

    12 V
    20 A supply


##############################################################################
# COOLING REQUIREMENTS
##############################################################################

Minimum

    Large Aluminum Heatsink

Better

    Fan-Cooled Heatsink

Best

    Water Block
    Pump
    Radiator

Never Operate

    TEC without heatsink

    TEC without airflow

    TEC without water circulation
    if water cooling is used


##############################################################################
# POWER EXAMPLE
##############################################################################

Cascade Example

TEC1

    4.31 V
    2.50 A

    10.77 W


TEC2

    6.81 V
    5.50 A

    37.43 W


Total

    48.20 W


Radiator Heat

    50.20 W


##############################################################################
# MAXIMUMS SUMMARY
##############################################################################

Manufacturer Published

Lowest Cold Side

    -40°C

Highest Hot Side

   +100°C


HSN Example Model

Lowest Calculated Tc

    -45.69°C

(not recommended for continuous operation)


Recommended Practical Targets

Cold Side

    -35°C

Hot Side

    +60°C or lower


##############################################################################
# LICENSE
##############################################################################

Creative Commons Attribution-NonCommercial-NoDerivatives 4.0

CC BY-NC-ND 4.0

You may:

    Share
    Copy
    Redistribute

You may not:

    Sell commercially
    Distribute modified versions
    Remove attribution

Provided AS-IS without warranty.

##############################################################################
# END README
##############################################################################
