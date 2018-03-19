---
UID: NS:ndis._NDIS_ENUM_FILTERS
title: "_NDIS_ENUM_FILTERS"
author: windows-driver-content
description: The NDIS_ENUM_FILTERS structure is returned from the call to the NdisEnumerateFilterModules function to provide filter information for a filter stack.
old-location: netvista\ndis_enum_filters.htm
old-project: netvista
ms.assetid: 0f57e226-dd60-4e62-8622-bfab5c66f537
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_ENUM_FILTERS, NDIS_ENUM_FILTERS, NDIS_ENUM_FILTERS structure [Network Drivers Starting with Windows Vista], PNDIS_ENUM_FILTERS, PNDIS_ENUM_FILTERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_ENUM_FILTERS, filter_structures_ref_4fe2a9d2-2539-40bc-9131-735a6337831e.xml, ndis/NDIS_ENUM_FILTERS, ndis/PNDIS_ENUM_FILTERS, netvista.ndis_enum_filters"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_ENUM_FILTERS
product: Windows
targetos: Windows
req.typenames: NDIS_ENUM_FILTERS, *PNDIS_ENUM_FILTERS
---

# _NDIS_ENUM_FILTERS structure
The NDIS_ENUM_FILTERS structure is returned from the call to the 
  <a href="..\ndis\nf-ndis-ndisenumeratefiltermodules.md">
  NdisEnumerateFilterModules</a> function to provide filter information for a filter stack.

## Syntax
````
typedef struct _NDIS_ENUM_FILTERS {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 Flags;
  ULONG                 NumberOfFilters;
  ULONG                 OffsetFirstFilter;
  NDIS_FILTER_INTERFACE Filter[1];
} NDIS_ENUM_FILTERS, *PNDIS_ENUM_FILTERS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     filter enumeration structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_ENUM_FILTERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_ENUM_FILTERS_REVISION_1.

`Flags`

Reserved for future use.

`NumberOfFilters`

The number of filter information structures that are included in the array in the 
     <b>Filter</b> member.

`OffsetFirstFilter`

The offset, in bytes, to the first member of array at the 
     <b>Filter</b> member from the beginning of the NDIS_ENUM_FILTERS structure.

`Filter`

An array that contains zero or more 
     <a href="..\ndis\ns-ndis-_ndis_filter_interface.md">NDIS_FILTER_INTERFACE</a> structures that
     the call returns.

## Remarks
The 
    <a href="..\ndis\nf-ndis-ndisenumeratefiltermodules.md">
    NdisEnumerateFilterModules</a> function returns an NDIS_ENUM_FILTERS structure and the 
    <b>Filter</b> member of that structure contains an array of 
    <a href="..\ndis\ns-ndis-_ndis_filter_interface.md">NDIS_FILTER_INTERFACE</a> structures. The
    array contains one NDIS_FILTER_INTERFACE structure for each NDIS 5.1 or earlier filter intermediate
    driver or NDIS 6.0 or later NDIS filter module that is in the driver stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nf-ndis-ndisenumeratefiltermodules.md">NdisEnumerateFilterModules</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_filter_interface.md">NDIS_FILTER_INTERFACE</a>