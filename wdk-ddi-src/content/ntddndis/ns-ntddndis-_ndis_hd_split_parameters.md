---
UID: NS:ntddndis._NDIS_HD_SPLIT_PARAMETERS
title: "_NDIS_HD_SPLIT_PARAMETERS"
author: windows-driver-content
description: The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport adapter.
old-location: netvista\ndis_hd_split_parameters.htm
old-project: netvista
ms.assetid: 1cc76765-871e-4cd0-b927-b0b4d3d746b4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_HD_SPLIT_PARAMETERS, PNDIS_HD_SPLIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_HD_SPLIT_PARAMETERS, header_data_split_ref_f7f3a3c4-4259-44a5-abce-fa393922f97d.xml, netvista.ndis_hd_split_parameters, ntddndis/NDIS_HD_SPLIT_PARAMETERS, ntddndis/PNDIS_HD_SPLIT_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_HD_SPLIT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_HD_SPLIT_PARAMETERS, *PNDIS_HD_SPLIT_PARAMETERS
---

# _NDIS_HD_SPLIT_PARAMETERS structure
The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport
  adapter.

## Syntax
```
typedef struct _NDIS_HD_SPLIT_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              HDSplitCombineFlags;
} *PNDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS;
```

## Members


`Header`

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     provider characteristics structure (NDIS_HD_SPLIT_PARAMETERS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_ HD_SPLIT_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_PARAMETERS_REVISION_1.

`HDSplitCombineFlags`

A set of flags that specify the current header-data split settings of a miniport adapter. A
     protocol driver or user-mode application can specify a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_COMBINE_ALL_HEADERS

The miniport adapter should combine split frames. If header-data split is enabled in the
       hardware, the miniport driver should combine the header and data before indicating the frame to
       NDIS.

## Remarks
The NDIS_HD_SPLIT_PARAMETERS structure is used in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569587">OID_GEN_HD_SPLIT_PARAMETERS</a> OID set
    request to specify the current header-data split settings of a miniport adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.1 and later. Supported in NDIS 6.1 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569587">OID_GEN_HD_SPLIT_PARAMETERS</a>