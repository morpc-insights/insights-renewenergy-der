# Data Kit - Distributed Energy Resources

## Version

Current version: 2025-02-22

## Provider

  - Organization: [Mid-Ohio Regional Planning Commission](https://morpc.org)
  - Contact: 
    - Name: Adam Porr
	- E-mail: aporr@morpc.org
	- Phone: 614-233-4216

## Introduction

The Public Utilities Commission of Ohio maintains a [database](https://maps.puco.ohio.gov/arcgis/rest/services/electric/Distributed_Energy_Resources/MapServer/0/) containing the locations and attributes of distributed energy resources (DER) facilities and an associated [dashboard](https://maps.puco.ohio.gov/portal/apps/dashboards/ef2586cbf54b42cd8f5af3cf5c5da296). The dashboard notes that a distributed energy resource (DER) is a source of electric power that is not directly connected to a bulk power system. DER includes both generators and energy storage technologies capable of exporting active power to the electric grid.  This data kit includes a summary of DER facilities for the MORPC 15-county region and the counties and communities therein. 

## Outputs

This data kit includes a long form table in CSV format (see `./output_data/renewenergy-der-long.csv`) which provides a count of DER facility registrations and generating capacity indexed by geographic identifier, year, and fuel type.
  
The data is accompanied by a [Frictionless Resource file](https://specs.frictionlessdata.io/data-resource/), which provides a high-level description of the data and a link to the associated table schema.  The Resource file also provides the [MD5 checksum](https://en.wikipedia.org/wiki/Md5sum) ("hash") and the file size ("bytes") of the data file to allow for integrity checking.

The table schema is described by a [Frictionless Schema file](https://specs.frictionlessdata.io/table-schema/), which describes each of the fields contained in the table, including its name and type, and sometimes provides additional metadata about the table.

## Processes

The output table is is produced by a [Jupyter notebook](https://jupyter.org/) (see `./renewenergy-der.ipynb`).

The process is fully automated, but depends on outputs from several upstream processes.

## Inputs

The process requires the following inputs:

  1. Summarized data for the DER facilities, which is produced by upstream process [morpc-renewenergyfacilities-summarize](https://github.com/morpc/morpc-renewenergyfacilities-summarize). See `./input_data/morpc-renewenergyfacilities-der-long.csv`.
  1. MORPC standard geographies lookup table, which is produced by upstream process [morpc-geos-collect](https://github.com/morpc/morpc-geos-collect)
  1. [MORPC's member list](https://github.com/morpc/morpc-lookup/blob/main/Member_List.xlsx)
  
Note that access to some of the upstream content is restricted to MORPC staff.

## Revision history

Revisions are listed in reverse chronological order.

### 2025-02-22 Adam Porr <aporr@morpc.org>

Initial release.