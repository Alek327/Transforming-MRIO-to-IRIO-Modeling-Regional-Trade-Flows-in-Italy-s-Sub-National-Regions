
Explanation of the Code

1. Internal Production Calculation (Steps 1-4):
   - The code begins by calculating the internal production for five Italian sub-national regions: Northwest (NW), Northeast (NE), Central (CN - Toscana), Mediterranean (MEZ - Centro), and External (Ext - Sud).
   - Internal Production Matrices: These matrices represent the production within each region that is used internally. They are calculated by post-multiplying the total flow matrices (representing the total output of each region) by a diagonal matrix of internal production shares. These shares are determined by subtracting the ratio of intermediate imports (both interregional and international) to the total resources available for each commodity from 1. This ratio, called `dint`, reflects the portion of total resources that is imported rather than produced internally.

2. Interregional Intermediate Imports (Steps 5-7):
   - Interregional Trade Flows: The code replaces the row corresponding to interregional intermediate imports for each region with a matrix of intersectoral import flows. These matrices are constructed by pre-multiplying the diagonalized vector of interregional imports from other regions by the row share matrix of intermediate purchases. This ensures that the imports are allocated proportionally across the different sectors based on their share of total intermediate flows.
   - For each region (NW, NE, CN, MEZ, Ext), the code calculates how much intermediate input is imported from other Italian regions. This is done by adjusting the intermediate purchases of each sector based on the interregional trade data available.

3. International Intermediate Imports (Step 7):
   - International Imports: The code similarly handles international imports by creating a matrix of intersectoral flows for these imports. For each region, the diagonalized vector of international imports is pre-multiplied by the row share matrix of intermediate purchases. This step adjusts the total flow matrix to account for the proportion of inputs that come from outside Italy, ensuring that these imports are properly integrated into the region’s production structure.

4. Final Consumption Internal Production (Steps 9-11):
   - Final Consumption Matrices: The internal production that is consumed within the region (final consumption) is calculated by post-multiplying the final consumption matrix by the diagonalized vector of internal production shares. These shares are derived by subtracting the ratio of final import streams (both interregional and international) to total final consumption for each good from 1. This step allows the code to distinguish between goods consumed domestically and those imported, ensuring that only domestically produced goods are counted in the region’s internal production.

5. Interregional Final Exports (Steps 12-13):
   - Final Exports: For interregional final exports, the code replaces the column vector of intermediate exports with matrices of final export flows. Each of these matrices is constructed by pre-multiplying the diagonalized vector of final interregional exports from one region to another by the row share matrix of intermediate purchases for the destination region. This process adjusts the total flow matrix to accurately reflect the flow of goods between regions within Italy.
   - The code computes the final exports for each region, ensuring that these are allocated according to the intermediate purchases structure of the receiving region, which helps model the interregional trade accurately.

6. External Exports (Remaining Unchanged):
   - Exports Abroad: The code leaves the column vector of exports abroad unchanged, as these do not need to be adjusted by interregional flows. These exports represent goods and services that are sold outside of Italy and are not influenced by the internal trade structure within Italy.

### Methodology and Purpose
This methodology transforms a Multi-Regional Input-Output (MRIO) table into an Interregional Input-Output (IRIO) table that accurately reflects trade among the Italian sub-regions. The resulting IRIO table provides a more detailed picture of regional trade flows, which can be used to inform economic modeling, including how regional production and consumption adapt to changes in income, wealth, and prices.

- Production Module: The IRIO table feeds into the production module, capturing intermediate trade among Italian regions.
- Final Demand Module: It also informs the final demand module, where household consumption is adjusted based on regional economic conditions.

This transformation allows for a more precise analysis of regional economies within Italy, offering insights into how interregional and international trade affects regional production, consumption, and overall economic dynamics.
