# Power BI - Export all visuals
Python notebook to embed a report and then export every visual to CSV and/or Excel files

## Introduction

This notebook embeds a Power BI report in an interactive frame and then attempts to export the data from every visual on every (non-hidden) page. Note that not every visual type supports data export.

The data is exported in CSV and/or Excel format (both by default). A folder is created for the output, then a sub-folder is created for each page, and a file is created for each visual.

To run this, you will need to obtain your group (workspace) id and report id, e.g. from the URL of your report.  The target report must be published in a workspace.

## Requirements

- a Power BI report, published to a workspace
- a Power BI account with access to the report
- Python notebook environment e.g. [Visual Studio Code](https://code.visualstudio.com/download) configured for [python and the Jupyter extension](https://code.visualstudio.com/docs/languages/python)
- Python packages installed (eg pip install ...)
  - pandas
  - powerbiclient
- VS Code Extension [Compare Folders](https://marketplace.visualstudio.com/items?itemName=moshfeu.compare-folders) (optional)

## Use cases & notes

This project is mainly intended to help test Power BI reports. Any change to a report's input data, queries, semantic model, or page designs can affect the results shown to the end users. This project can quickly capture snapshots of all the data presented in open formats (CSV, Excel) that can be independently reviewed and compared using a range of tools and techniques. 

When used to produce CSV files, the project can be used in combination with the Visual Studio Code "Compare Folders" Extension to very quickly compare every cell of data from every visual in the report. This could be useful for a "regression test" to determine whether changes between versions have only had the desired effect and have not leaked into other pages or visuals.  That extension cannot compare Excel files, so if those are present in the target folders you can bypass them by adding "**/*.xlsx" to the Extension settings, Compare Folders: Exclude filter.

The notebook embeds a live frame containing the target report. So if you need to first apply specific filters or use slicers, you can run the notebook cell-by-cell down to get the embedded report frame, then interact with it just like it was a Power BI web browser tab.  When you run the remaining notebook cells, the output will reflect your filter or slicer changes. Any changes made will not be saved back to the Power BI web report definition.

## Credits & Acknowledgements

This project started from a Microsoft sample notebook - refer to that for more possibilities for automated report interactions:

https://learn.microsoft.com/en-us/javascript/api/overview/powerbi/powerbi-jupyter

## 🤝 Support

Contributions, issues, feature requests and sponsorship are all welcome!

Give a ⭐️ if you like this project!
