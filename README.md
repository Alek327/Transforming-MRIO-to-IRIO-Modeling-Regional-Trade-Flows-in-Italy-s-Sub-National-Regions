# Interregional Input-Output Table Transformation for Italian Sub-Regions

This repository contains R code that transforms a Multi-Regional Input-Output (MRIO) table into an Interregional Input-Output (IRIO) table specifically tailored for five Italian sub-regions: Northwest (NW), Northeast (NE), Central (CN - Toscana), Mediterranean (MEZ - Centro), and External (Ext - Sud). This transformation is crucial for accurately reflecting the trade dynamics among these regions.

## Overview

The IRIO model created through this code is designed to provide a detailed representation of interregional trade flows within Italy. The model is used to feed both the Production and Final Demand modules of economic models, which are critical for understanding regional economic behaviors in response to changes in income, wealth, and prices.

### Steps in the Transformation Process

1. **Internal Production Calculation**:
   - The regional intersectoral exchange matrices (internal production matrices) are calculated by adjusting the total flow matrices with the share of intermediate flows that are produced internally. This share is computed by subtracting the ratio of intermediate imports (both interregional and international) to total resources from 1. This ensures that only the internally produced portion of goods is included in the internal production matrices.

2. **Interregional Intermediate Imports**:
   - The interregional intermediate imports for each region are calculated by creating matrices of intersectoral import flows. These matrices adjust the total flow matrix to reflect the proportion of intermediate inputs imported from other Italian regions, ensuring accurate representation of interregional trade.

3. **International Intermediate Imports**:
   - Similarly, international imports are incorporated by constructing matrices that represent the flows of imported goods from outside Italy into each region. This adjustment is crucial for integrating international trade into the regional economic structure.

4. **Final Consumption of Internal Production**:
   - The code calculates the internal production consumed within each region by adjusting the final consumption matrix with the internal production shares. This step distinguishes between goods consumed domestically and those imported, ensuring that the IRIO table accurately reflects the regional consumption of internally produced goods.

5. **Interregional Final Exports**:
   - The final exports to other Italian regions are calculated by constructing matrices that represent the flows of goods between regions. These matrices are adjusted based on the structure of intermediate purchases in the receiving region, providing a detailed view of interregional trade flows.

6. **Exports Abroad**:
   - The exports abroad (outside of Italy) are kept unchanged in the transformation process, as they do not depend on interregional trade dynamics.

## Methodology

This methodology transforms the MRIO table into an IRIO table that provides a more granular view of interregional trade among the Italian sub-regions. The IRIO table is essential for:
- **Production Module**: Capturing intermediate trade flows among regions.
- **Final Demand Module**: Modeling how household consumption changes based on regional economic conditions, such as income and wealth.

The IRIO model developed through this code allows for detailed economic analysis, helping policymakers and researchers understand the complex trade relationships within Italy and how they impact regional economies.

## Usage

To use the code, ensure you have the required input data, including the MRIO table and interregional trade data for 2019. The code is structured to handle these inputs and produce the IRIO table, which can be used for further economic analysis.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributions

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## Contact

For any questions or further information, please contact [Your Name] at [Your Email].
