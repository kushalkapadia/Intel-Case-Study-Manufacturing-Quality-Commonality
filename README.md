# Intel-Case-Study-Manufacturing-Quality-Commonality
In Intel, a commonality is a common characteristic among a collection of lots/units. More specifically here, a commonality is a characteristic of the bad lots/units. The purpose of commonality analysis is to determine potenial causes for differences in process/station performance, yield, quality or reliability. 

# Questions answered:

1] Graphical assessment of the defect percentage for each LOT_ID by UNIT_PROCESS_DATE to show the time trend. Indicate a time frame in which the problem occured. 

2] Determine which of the 13 parameters could be associated with the increase in defective units.

3] Other than these 13 parameters, are there any variables that can be associated with the increase in defective units?

4] [Bonus] From an analysis and data collection perspective, what methods of control could be implemented to detect such a problem while processing the units thereby preventing such an increase in defects?


## A little more deep dive into the problem at hand:

The assembly and test production model employs a form of batch processing. In batch processing, groups of units are processed together through different stations along the manufacturing process flow. These stations perform different functions to either add value or test the units. These batches or collection of units are referred to as Lots. This type of manufacturing creates an additional
layer of variability. There exists unit level variability as well as lot level variability.
![intel_diagram](https://user-images.githubusercontent.com/33611104/53622660-c9ab2000-3bb7-11e9-8033-229c1c9ed44d.png)

For this case study, the station that performs the final testing of the units has noticed some irregularities
regarding the failure rate of the units. The failures can be caused by the supplier sourced incoming raw material
used to assemble the units, the tools used the process the units, or some combination of these factors.

## Some information about the two CSV files used:

Unit_Level.csv - This file contains all measurements collected on each unit throughout the process flow.
 UNIT_ID: Unique identifier for each unit
 UNIT_PROCESS_DATE: Date in which unit/lot was processed
 PARAMETER#: 13 measurements collected on each unit generically labeled as PARAMETER1 though PARAMETER
13
 UNIT_CARRIER_POS_X: Units are processed within a tray that has 10 pockets. This is the x location of pocket the
unit was processed within.
 UNIT_CARRIER_POS_Y: Units are processed within a tray that has 10 pockets. This is the y location of pocket the
unit was processed within.
 RESPONSE_FLAG: The final test result for the unit. 0 is a pass. 1 is a fail.

Lot_Level.csv – This file contains all other information associated with the units and lots. This is additional data
to view the specific tools that processed the units as well as properties of the raw materials that were used to
assemble the units.
 UNIT_ID: Unique identifier for each unit.
 LOT_ID: Lot identifier for the lot in which the unit was processed.
 MATERIAL#_SUPPLIER: Name of the raw materials supplier used in Intel’s manufacturing process.
 MATERIAL#_SUPPLIER_LOT_ID: Lot identifier used by the raw materials supplier in the manufacturing of their
materials.
 MATERIAL2_SUPPLIER_FACILITY: Material Supplier 2 produces the raw material in different facilities. This is the
supplier facility in which the material was produced.
 FAJ_TOOL_ID: FAJ is an assembly station in the Intel Manufacturing process that can impact any of the 13
parameters measured on each unit. FAJ_TOOL_ID is the identification label of the specific tool upon which the unit
was processed.
 VD_TOOL_ID: VD is an assembly station in the Intel Manufacturing process that can impact any of the 13
parameters measured on each unit. VD_TOOL_ID is the identification label of the specific tool upon which the unit
was processed.
 VD_TOOL_LANE: The VD Tool contains two routes in which units can be processed, either FRONT or BACK lane. The
lanes are determined by unit position in the tray. (Tray position y = 0 implies Front Lane and Tray position y = 1
implies Back Lane)
 NX_TOOL_ID: NX is an assembly station in the Intel Manufacturing process that can impact any of the 13
parameters measured on each unit. NX_TOOL_ID is the identification label of the specific tool upon which the unit
was processed.
 NX_TOOL_COMPARTMENT: The NX Tool contains two compartments in which units can be processed, either TOP
or BOTTOM.
