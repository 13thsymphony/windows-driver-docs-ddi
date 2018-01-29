---
UID : NS:ntddrilapitypes.RILUICCCMDPARAMETERS
title : RILUICCCMDPARAMETERS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riluicccmdparameters.htm
old-project : netvista
ms.assetid : 02c37c3d-fa5b-4d26-a092-09f6f3dbd46c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.riluicccmdparameters, RILUICCCMDPARAMETERS, ntddrilapitypes/RILUICCCMDPARAMETERS, RILUICCCMDPARAMETERS structure [Network Drivers Starting with Windows Vista], *LPRILUICCCMDPARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddrilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILUICCCMDPARAMETERS, *LPRILUICCCMDPARAMETERS
---

# RILUICCCMDPARAMETERS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCCMDPARAMETERS {
  DWORD            cbSize;
  DWORD            dwParams;
  RILUICCFILEPATH  filePath;
  DWORD            dwParameter1;
  DWORD            dwParameter2;
  DWORD            dwParameter3;
} RILUICCCMDPARAMETERS, RILUICCCMDPARAMETERS;
````

## Members


`cbSize`



`dwParameter1`



`dwParameter2`



`dwParameter3`



`dwParams`



`filePath`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |