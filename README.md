<img width="699" height="104" alt="image" src="https://github.com/user-attachments/assets/2b1c5af5-0c09-4e7e-9136-549ad4c2d0e2" />


# ArcGIS Online (AGOL) Field Metadata Updater

## Overview
This script streamlines the process of updating a feature service's field metadata (alias/description/value type --> see resource on field value types: https://doc.arcgis.com/en/arcgis-online/manage-data/describe-fields.htm#ATTFIELD_VALUETYPES) on ArcGIS Online (AGOL) thereby eliminating the need for manual entry using AGOL's interface. For this script to run successfully, it is recommended that you already have field metadata information ready for your service. This script was inspired by Lisa Berry's Hosted Feature Service Alias Updater script: https://github.com/lisaberrygis/AliasUpdater/. 

Created by: Farah Hoque, Esri Canada (2026). For comments regarding this tool, please contact fhoque@esri.ca

## Why was this script created?
This script was created as a way to quickly update field metadata of feature services with multiple layers and many fields (30+) which would be cumbersome to do manually through AGOL's interface. The saved lookup table can also be used to recover a service's field metadata after it gets wiped out during an overwrite.  

## Who is this script for?
Anyone who wants to make their feature service more user-friendly and AI compatible.

## What can this script do?
The AGOL Field Metadata Updater has 2 main portions:
1. **Extracts** existing alias, description, and value type of fields in a feature service containing one or more layers and saves as a lookup table inside a folder. For a feature service with multiple layers, the lookup table will save each layer as a sheet with the layer name and layer ID. The user then needs to fill out the lookup table (see the attached SampleLookupTable.xlsx)
2. **Updates** the service on ArcGIS Online using the lookup table.

## Instructions
Download the AGOL_FieldMetadataUpdater_FH.py script and run it using any python IDEs (i.e., PyCharm, Visual Studio Code) that is configured with ArcGIS Pro. To execute the script, scroll down to the def main() function and enter the parameters required.

<b>Use Case #1: Generate a lookup table by extracting existing field metadata (alias/description/value type) from the feature service. </b> In this case, users can fill in the alias and description and select an appropriate value type from the list of options directly in the lookup table.

<b>Use Case #2: Modify your own lookup table to fit the schema of the lookup table required for this tool. </b> For this case, download the SampleLookupTable.xlsx and modify your lookup table to have the same column headers as the sample lookup table. For the field value types, provide the corresponding 'JSON Field Value Type' value (see table below) required for updating the field value type in ArcGIS Online's backend. In the script, after entering the parameters and pointing to your lookup table, comment out the 'Part 1: Create lookup table' portion and just proceed to 'Part 2' updating the service on ArcGIS Online.

<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th>Field Value Type</th>
      <th>JSON Field Value Type</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Name or Title</td><td>nameOrTitle</td></tr>
    <tr><td>Description</td><td>description</td></tr>
    <tr><td>Type or Category</td><td>typeOrCategory</td></tr>
    <tr><td>Count or Amount</td><td>countOrAmount</td></tr>
    <tr><td>Percentage or Ratio</td><td>percentageOrRatio</td></tr>
    <tr><td>Measurement</td><td>measurement</td></tr>
    <tr><td>Currency</td><td>currency</td></tr>
    <tr><td>Unique Identifier</td><td>uniqueIdentifier</td></tr>
    <tr><td>Ordered or Ranked</td><td>orderedOrRanked</td></tr>
    <tr><td>Binary</td><td>binary</td></tr>
    <tr><td>Location or Place Name</td><td>locationOrPlaceName</td></tr>
    <tr><td>Coordinate</td><td>coordinate</td></tr>
    <tr><td>Date and Time</td><td>dateAndTime</td></tr>
  </tbody>
</table>

<b>Use Case #3: Re-apply field metadata after a service overwrite. </b> For this case, after entering the parameters and pointing to an existing lookup table, comment out the 'Part 1: Create lookup table' portion and just proceed to updating the service on ArcGIS Online. 

## Requirements
- You must have ArcGIS Pro installed on your computer
- You must own the service you are trying to update


