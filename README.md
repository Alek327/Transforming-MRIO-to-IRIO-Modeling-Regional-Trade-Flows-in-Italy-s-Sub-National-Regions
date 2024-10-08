# Interregional Input-Output Table Transformation for Italian Sub-Regions

This R script transforms a Multi-Regional Input-Output (MRIO) table into an Interregional Input-Output (IRIO) table specifically tailored for six Italian sub-regions: Northwest (NW), Northeast (NE), Toscana, Centro, Sud, and External (Ext). This transformation is crucial for accurately reflecting the trade dynamics among these regions.

## Overview

The IRIO model created through this script provides a detailed representation of interregional trade flows within Italy. The model feeds both the Production and Final Demand modules of economic models, which are critical for understanding regional economic behaviors in response to changes in income, wealth, and prices.

### Steps in the Transformation Process

1. **Internal Production Calculation**:
   - The internal production matrices for each region are calculated by adjusting the total flow matrices with the share of intermediate flows produced internally. This share is computed by subtracting the ratio of intermediate imports (both interregional and international) to total resources from 1. This process ensures that only the internally produced portion of goods is captured in the internal production matrices.

2. **Interregional Intermediate Imports**:
   - Interregional intermediate imports for each region are calculated by creating matrices of intersectoral import flows. These matrices adjust the total flow matrix to reflect the proportion of intermediate inputs imported from other Italian regions, ensuring an accurate representation of interregional trade. The imports are combined from multiple regions, forming a clear picture of interregional trade dynamics.

3. **International Intermediate Imports**:
   - Interregional intermediate imports for each region are calculated by creating matrices of intersectoral import flows. These matrices adjust the total flow matrix to reflect the proportion of intermediate inputs imported from other Italian regions, ensuring an accurate representation of interregional trade. The imports are combined from multiple regions, forming a clear picture of interregional trade dynamics.

4. **Final Consumption of Internal Production**:
   - The internal production consumed within each region is calculated by adjusting the final consumption matrix with the internal production shares. This step ensures that the IRIO table accurately reflects the regional consumption of internally produced goods, distinguishing between domestic consumption and imported goods.

5. **Interregional Final Exports**:
   - Final exports to other Italian regions are calculated by constructing matrices representing the flows of goods between regions. These matrices are adjusted based on the structure of intermediate purchases in the receiving region, providing a detailed view of interregional trade flows.

6. **Exports Abroad**:
   - Exports abroad (outside of Italy) are incorporated into the transformation process, but they remain unchanged as they do not depend on interregional trade dynamics.
     
7. **Consistency Checks**:
   - To ensure accuracy, consistency checks are performed by comparing the row and column sums of the final table with expected totals for each region. These checks confirm that the interregional and international flows, as well as internal production, align with the total resources available in each region.
## Methodology

This methodology transforms the MRIO table into an IRIO table, offering a more granular view of This methodology transforms the MRIO table into an IRIO table, offering a more granular view of interregional trade among the Italian sub-regions. 

The IRIO model developed through this script enables detailed economic analysis, helping policymakers and researchers understand the complex trade relationships within Italy and how they impact regional economies.

## Usage

To use the script, ensure you have the required input data, including the MRIO table and interregional trade data for 2019. The code is structured to handle these inputs and produce the IRIO table, which can be used for further economic analysis.

## License

This project is released under the Creative Commons Zero v1.0 Universal (CC0 1.0) license. This means that the work has been dedicated to the public domain to the fullest extent permitted by law. You can copy, modify, distribute, and perform the work, even for commercial purposes, all without asking permission. See the LICENSE file for details.

## Contributions

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## Contact

For any questions or further information, please contact [Oleksandr Galychyn] at [ogalychyn@yahoo.com].
