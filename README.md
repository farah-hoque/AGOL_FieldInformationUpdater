# ArcGIS Online (AGOL) Field Information Updater

## Overview
This script streamlines the process of updating a feature service's field metadata (alias/description/value type) on ArcGIS Online (AGOL) thereby eliminating the need for manual entry using AGOL's interface. For this script to run successfully, it is recommended that you already have field metadata information ready for your service. This script was inspired by Lisa Berry's Hosted Feature Service Alias Updater script:https://github.com/lisaberrygis/AliasUpdater/tree/main. 

Created by: Farah Hoque, Esri Canada (2026)

## Who is this script for?
Anyone who wants to make their feature services more user-friendly and AI compatible.

## What can this script do?
The AGOL Field Information Updater has 2 main functions:
1. **Extracts** existing alias, description, and value type of fields in a feature service containing one or more layers and saves as a lookup table inside a folder. For a feature service with multiple layers, the lookup table will save each layer as a sheet with the layer name and layer ID.
2. **Updates** the service on ArcGIS Online using the lookup table.

## Requirements
- You must have ArcGIS Pro installed on your computer
- You must own the service you are trying to update


