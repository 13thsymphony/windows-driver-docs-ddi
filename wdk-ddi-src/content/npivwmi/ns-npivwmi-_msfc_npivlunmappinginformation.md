---
UID: NS:npivwmi._MSFC_NPIVLUNMappingInformation
title: "_MSFC_NPIVLUNMappingInformation"
author: windows-driver-content
description: The MSFC_NPIVLUNMappingInformation structure contains the Logical Unit Number (LUN) to virtual port mapping information.
old-location: storage\msfc_npivlunmappinginformation.htm
old-project: storage
ms.assetid: 5E8A2338-AF1E-41BE-870B-E1F1877DDEDD
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSFC_NPIVLUNMappingInformation, MSFC_NPIVLUNMappingInformation, MSFC_NPIVLUNMappingInformation structure [Storage Devices], PMSFC_NPIVLUNMappingInformation, PMSFC_NPIVLUNMappingInformation structure pointer [Storage Devices], _MSFC_NPIVLUNMappingInformation, npivwmi/MSFC_NPIVLUNMappingInformation, npivwmi/PMSFC_NPIVLUNMappingInformation, storage.msfc_npivlunmappinginformation"
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
-	MSFC_NPIVLUNMappingInformation
product: Windows
targetos: Windows
req.typenames: MSFC_NPIVLUNMappingInformation, *PMSFC_NPIVLUNMappingInformation
---

# _MSFC_NPIVLUNMappingInformation structure
The MSFC_NPIVLUNMappingInformation structure contains the Logical Unit Number (LUN) to virtual port mapping information.

## Syntax
```
typedef struct _MSFC_NPIVLUNMappingInformation {
  UCHAR WWPNVirtualPort[8];
  UCHAR WWPNPhysicalPort[8];
  UCHAR OSBus;
  UCHAR OSTarget;
  UCHAR OSLUN;
} MSFC_NPIVLUNMappingInformation, *PMSFC_NPIVLUNMappingInformation;
```

## Members


`WWPNVirtualPort`

The world wide port name of the virtual port.

`WWPNPhysicalPort`

The world wide port name of the physical port.

`OSBus`

The path ID of the LUN  mapped to the virtual port.

`OSTarget`

The target device ID number of the LUN mapped to the virtual port.

`OSLUN`

The LUN mapped to the virtual port.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | npivwmi.h (include Npivwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh127627">MSFC_NPIVLUNMappingInformation WMI Class</a>