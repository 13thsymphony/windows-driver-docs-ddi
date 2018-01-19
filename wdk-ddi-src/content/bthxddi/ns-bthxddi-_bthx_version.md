---
UID : NS:bthxddi._BTHX_VERSION
title : _BTHX_VERSION
author : windows-driver-content
description : The BTHX_VERSION structure describes the version or versions that the transport driver supports.
old-location : bltooth\bthx_version.htm
old-project : bltooth
ms.assetid : 2C5CC5B1-52F1-4DF5-9397-E8FD4983BA25
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _BTHX_VERSION, *PBTHX_VERSION, BTHX_VERSION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthxddi.h
req.include-header : BthXDDI.h
req.target-type : Windows
req.target-min-winverclnt : Versions: Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : _BTHX_VERSION
req.alt-loc : BthXDDI.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : "*PBTHX_VERSION, BTHX_VERSION"
---

# _BTHX_VERSION structure
The BTHX_VERSION structure describes the version or versions that the transport driver supports.

## Syntax
````
struct _BTHX_VERSION {
  ULONG Version;
};
````

## Members

        
            `Version`

            Bitmask of supported versions. Currently, BTHX_DDI_VERSION_1   is the only supported version.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthxddi.h (include BthXDDI.h) |