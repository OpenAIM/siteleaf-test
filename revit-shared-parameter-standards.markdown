---
title: Revit Shared Parameter Standards
date: 2018-10-29 03:25:00 Z
---

Shared Parameter Naming Standards

____

Current “Naming Conventions” Page:
In order for your shared parameter to be approved, you must follow our strict naming convention. This specific concatenation is as follows:
[Major][Minor][ModifierA][ModifierB]
Note that not all fields are required for every parameter. For example, Barcode has only one field and ApparentPowerInputPrimaryActual actually contains all four.
Example
AirFlowSupplyActual is a great example of how to use the standard naming convention:
AirFlow = Major
Supply = Minor
Actual = Modifier


Proposed “Naming Conventions” Page:
In order for your shared parameter to be approved, you must adhere to the following naming conventions: 
Naming Convention
[Major] [Minor] [ModifierA] [ModifierB]
Note that all fields NOT are required for every parameter. For example, Barcode has only one field and ApparentPowerInputPrimaryActual actually contains all four.
Example
AirFlowSupplyActual is an example of how to use the standard naming convention:
AirFlow = Major
Supply = Minor
Actual = Modifier
General Guidelines
A Shared Parameter name shall match an IFC Property name if 1)an IFC Property with the same meaning is available, 2)the IFC definition is clear, and 3)IFC Property only applies to one Revit Category. In the case that the IFC Property applies to more than one Revit Category, the Shared Parameter name shall be suffixed with the Revit Category name (see FireRating example below).
IFC Properties can be found in one of the following locations
IFC #7 Domain specific data schemas
IFC XSD 
BSDD
FireRating applies to many Revit Categories. For FireRating, the correct naming would be: FireRatingSlab, FireRatingStairs, FireRatingCovering, FireRatingPlate, FireRatingStructuralBeamSystems, FireRatingRamp, FireRatingChimney, FireRatingDoors, FireRatingWindows, FireRatingMember, FireRatingColumns, FireRatingStructuralColumns, FireRatingCurtainSystems, FireRatingRoofs, FireRatingWalls.
Separate parameters with unique names are required in order to 1) support the ability to contain different values (picklists, enumerations) for each type, and 2) to support identification of applicable Revit Category at time of selection and assignment. Mapping to IFC parameter names will occur through the OpenRFA IFC mappings.
Names shall not utilize existing parameter names, either existing built-in Revit System Parameters nor other Shared Parameters on OpenRFA.
Names shall not replicate the same meaning of an existing parameter with a different name.
For example: since BuildingId already exists, BuildingIdentification would be rejected.
Major and Minor shall go from general to specific.
Names must only consist of standard alphanumeric characters [A-Z] [a-z] [0-9]. 
Names shall not utilize the period character “.”, dash “-”, underscore “_”, space character “ “, or mathematical symbols as a field delimiter, separator, or otherwise. This is due to interferences with application behavior (CFD calculations and parameter value evaluation in Revit).
Naming shall use medial capitals, also known as Pascal Case or CamelCase
Acronyms are recommended to follow the CamelCase convention instead of retaining capitalization. For example EpaRating instead of EPARating.
Major
Major is recommended to align with the DATA TYPE, using one of the following:

Data Type
Recommended Major Value
Example
AREA
Area
AreaCoolingCoilFace
CURRENCY
Cost
CostAnnualOperatingAverage
ELECTRICAL_APPARENT_POWER
ApparentPower
ApparentPowerInputPrimaryActual
ELECTRICAL_CURRENT
Current
CurrentExhaustFanFullLoad
ELECTRICAL_FREQUENCY
Frequency
Frequency
ELECTRICAL_POTENTIAL
Potential
VoltageInputPrimaryActual
ELECTRICAL_POWER
Hp
Power
HpFanCoolingTower
PowerFanExhaust
ELECTRICAL_WATTAGE
Wattage
WattageOperatingDesign
FORCE
n/a


HVAC_AIR_FLOW
AirFlow
AirFlowAirTerminal
HVAC_COOLING_LOAD
CoolingLoad
CoolingLoadLatentDesign
HVAC_DUCT_SIZE
n/a


HVAC_HEATING_LOAD
n/a


HVAC_PRESSURE
Pressure
PressureAirTerminalStatic
HVAC_TEMPERATURE
Temperature
TemperatureAmbientMinimum
HVAC_VELOCITY
Velocity
VelocityFanOutlet
INTEGER
n/a


LENGTH
n/a


LOADCLASSIFICATION
LoadClassification
LoadClassificationPrimary
MATERIAL
Material
MaterialCodingColor
NOOFPOLES
n/a


NUMBER
n/a


PIPE_SIZE
PipeSize
PipeSizeFilterInlet
PIPING_FLOW
PipingFlow
PipingFlowChilledWaterActual
PIPING_PRESSURE
PipingPressure
PipingPressureInlet
PIPING_TEMPERATURE
Temperature
TemperatureChilledWaterEntering
TEXT
n/a


URL
Link
LinkProductDocumentation
VOLUME
n/a


YESNO
Is 
Has
Visible
IsCalculateLoadVfd
HasDemandControlVentilation
VisibleClearanceAreas

Minor
???
When there need to be more than one of a particular parameter on a family, do not number the first one and the second shall start with 2
AirFlowExhaustActual
AirFlowExhaustDesign
AirFlowExhaust2Actual
AirFlowExhaust2Design

Modifier
Modifier may be one of the following:
Value
Definition
Example
Design
Basis of Design values, performance criteria
PipingFlowChilledWaterDesign
Actual
Actual performance characteristics correlating to Basis of Design or performance criteria “Design” values
PipingFlowChilledWaterActual
Max
Maximum value, commonly associated as a range with a corresponding Min value. Use of “Max” is recommended instead of “Maximum” as it is more compact.
Exampl
Min
Minimum value, commonly associated as a range with a corresponding Max value. Use of “Min” is recommended instead of “Minimum” as it is more compact.
Example
System Type
A specific system designation, commonly associated with 
AirFlowSupplyDesign, AirFlowReturnDesign, AirFlowExhaustDesign,
PowerInputCoolingNominal,
PowerInputHeatingNominal


Height




Width




Diameter




Peak


RatingEnergyEfficiencyPeak
Seasonal


RatingEnergyEfficiencySeasonal
Failure


RatingEnergyEfficiencyFailure
Inlet


PipingFlowFilterInlet
Outlet


PipingFlowFilterOutlet
Operating


PipingPressureOperating
Type




Size




Proposed “OpenRFA Terminology” Page:

OpenRFA defines the following words as they should be interpreted in the application of OpenRFA products. These terms clarify requirements levels and are derived from the IETF 2119 best practices.

1. "MUST": This word, or the terms "REQUIRED" or "SHALL", mean that the definition is an absolute requirement of the specification.

2. "MUST NOT": This phrase, or the phrase "SHALL NOT", mean that the definition is an absolute prohibition of the specification.

3. "SHOULD": This word, or the adjective "RECOMMENDED", mean that there may exist valid reasons in particular circumstances to ignore a particular item, but the full implications must be understood and carefully weighed before choosing a different course.

4. "SHOULD NOT": This phrase, or the phrase "NOT RECOMMENDED" mean that there may exist valid reasons in particular circumstances when the particular behavior is acceptable or even useful, but the full implications should be understood and the case carefully weighed before implementing any behavior described with this label.

5. "MAY": This word, or the adjective "OPTIONAL", mean that an item is truly optional. One vendor may choose to include the item because a particular marketplace requires it or because the vendor feels that it enhances the product while another vendor may omit the same item. An implementation which does not include a particular option MUST be prepared to interoperate with another implementation which does include the option, though perhaps with reduced functionality. In the same vein an implementation which does include a particular option MUST be prepared to interoperate with another implementation which  does not include the option (except, of course, for the feature the option provides.)



Proposed “Condensed Revit Family Category” List:
Derived from: “Classification Manager Database US.xlsx”

DISCIPLINE
CONDENSED REVIT FAMILY CATEGORY
General
DetailItems
General
GenericModels
General
Materials
General
Profiles
General
ProjectInformation
General
SpecialtyEquipment
Architecture
Areas
Architecture
Balusters
Architecture
Casework
Architecture
Ceilings
Architecture
Columns
Architecture
CurtainPanels
Architecture
CurtainSystems
Architecture
CurtainWallMullions
Architecture
Doors
Architecture
Entourage
Architecture
Floors
Architecture
Furniture
Architecture
FurnitureSystems
Architecture
Mass
Architecture
Opening
Architecture
Pads
Architecture
Parking
Architecture
Planting
Architecture
Railings
Architecture
Ramps
Architecture
Roads
Architecture
Roofs
Architecture
Rooms
Architecture
Site
Architecture
Stairs
Architecture
Topography
Architecture
Walls
Architecture
Windows
MEP
AirTerminals
MEP
CableTrayFittings
MEP
CableTrays
MEP
CommunicationDevices
MEP
ConduitFittings
MEP
Conduits
MEP
DataDevices
MEP
DuctAccessories
MEP
DuctFittings
MEP
DuctSystems
MEP
Ducts
MEP
ElectricalEquipment
MEP
ElectricalFixtures
MEP
FireAlarmDevices
MEP
FlexDucts
MEP
FlexPipes
MEP
HVACZones
MEP
LightingDevices
MEP
LightingFixtures
MEP
MechanicalEquipment
MEP
NurseCallDevices
MEP
PipeAccessories
MEP
PipeFittings
MEP
Pipes
MEP
PipingSystems
MEP
PlumbingFixtures
MEP
SecurityDevices
MEP
Spaces
MEP
Sprinklers
MEP
SwitchSystem
MEP
TelephoneDevices
MEP
Wires
Structural
BoundaryConditions
Structural
RebarShape
Structural
StructuralAreaReinforcement
Structural
StructuralBeamSystems
Structural
StructuralColumns
Structural
StructuralConnections
Structural
StructuralFoundations
Structural
StructuralFraming
Structural
StructuralPathReinforcement
Structural
StructuralRebar
Structural
StructuralStiffeners
Structural
StructuralTrusses


Proposed “Frequently Asked Question” Page:
Revit allows Shared Parameters names to change while retaining the original GUID and continue to schedule correctly.
Is there a way to batch modify parameters in my project and content library from my current usage to come in compliance with OpenRFA approved parameters?



Issues Identified:
Name selection process
Revit System Parameters
IFC Property Set as grouping
IFC Property Set Properties
Custom Shared Parameters
What about recommended Acronyms; RPSS list?
Discussion:
http://openrfa.org/forum/topic/parameter-groups



BSDD Original List for Fire Rating example
http://bsdd.buildingsmart.org/#concept/search 

slab common . fire rating, fire rating
stair common . fire rating, fire rating
covering common . fire rating, fire rating
plate common . fire rating, fire rating
beam common . fire rating, fire rating
building element proxy common . fire rating, fire rating
ramp common . fire rating, fire rating
chimney common . fire rating, fire rating
door common . fire rating, fire rating
window common . fire rating, fire rating
member common . fire rating, fire rating
column common . fire rating, fire rating
curtain wall common . fire rating, fire rating
roof common . fire rating, fire rating
fire rating
