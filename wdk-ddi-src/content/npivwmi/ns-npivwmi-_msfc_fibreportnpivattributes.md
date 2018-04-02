---
UID: NS:npivwmi._MSFC_FibrePortNPIVAttributes
title: "_MSFC_FibrePortNPIVAttributes"
author: windows-driver-content
description: The MSFC_FibrePortNPIVAttributes structure contains attribute information for the virtual ports on an adapter.
old-location: storage\msfc_fibreportnpivattributes.htm
old-project: storage
ms.assetid: 1641C3A0-E6D9-4E30-9E3C-3C09A14F591F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSFC_FibrePortNPIVAttributes, MSFC_FibrePortNPIVAttributes, MSFC_FibrePortNPIVAttributes structure [Storage Devices], PMSFC_FibrePortNPIVAttributes, PMSFC_FibrePortNPIVAttributes structure pointer [Storage Devices], _MSFC_FibrePortNPIVAttributes, npivwmi/MSFC_FibrePortNPIVAttributes, npivwmi/PMSFC_FibrePortNPIVAttributes, storage.msfc_fibreportnpivattributes"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: npivwmi.h
req.include-header: Npivwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	npivwmi.h
api_name:
-	MSFC_FibrePortNPIVAttributes
product:
- Windows
targetos: Windows
req.typenames: MSFC_FibrePortNPIVAttributes, *PMSFC_FibrePortNPIVAttributes
---

# _MSFC_FibrePortNPIVAttributes structure
The MSFC_FibrePortNPIVAttributes structure contains attribute information for the virtual ports on an adapter.

## Syntax
```
typedef struct _MSFC_FibrePortNPIVAttributes {
  UCHAR                           WWPN[8];
  UCHAR                           WWNN[8];
  ULONG                           NumberVirtualPorts;
  MSFC_VirtualFibrePortAttributes VirtualPorts[1];
} MSFC_FibrePortNPIVAttributes, *PMSFC_FibrePortNPIVAttributes;
```

## Members


`WWPN`

The world wide port name of the physical port.

`WWNN`

The world wide node name of the physical port.

`NumberVirtualPorts`

The number of virtual ports on the adapter.

`VirtualPorts`

An array of virtual ports. The array length is specified in the <b>NumberVirtualPorts</b> member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | npivwmi.h (include Npivwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh127624">MSFC_FibrePortNPIVAttributes WMI Class</a>