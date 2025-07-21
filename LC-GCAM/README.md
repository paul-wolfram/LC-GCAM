# LC-GCAM
Tool for performing life cycle analysis of fuel technologies in GCAM

## Description
LC-GCAM calculates life cycle greenhouse gas emissions and energy intensities using output from GCAM. This repository contains the data and R code to run the model and reproduce the results presented in the paper: Do multi-sector dynamics models and life cycle assessment models agree? Comparing GCAM’s with GREET’s fuel life cycle estimates.

In addition to core model scripts, the repository includes several mapping files that support a full upstream analysis of inputs to any energy technology—capturing primary energy use, non-CO₂ emissions, and CO₂ storage. The method recursively traces each technology’s input chains, collapsing each GCAM sector into a set of energy input-output coefficients, CO₂ storage factors, and non-CO₂ emission factors, all normalized per unit of sectoral output.

A user-defined recursion depth determines how many steps upstream the analysis will extend. Lower values may overlook relevant upstream energy contributions, while higher values may increase computation time with limited additional insight if contributions fall below reporting thresholds.

Note: Due to GCAM’s treatment of traded commodities—where all global trade is resolved within the USA region—this method currently returns reliable results only for the USA. For non-U.S. regions, adjustments are necessary for commodities whose primary energy footprint includes imports.