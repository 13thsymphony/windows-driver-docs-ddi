---
UID : NS:hbapiwmi._SM_AddPort_OUT
title : _SM_AddPort_OUT
author : windows-driver-content
description : The SM_AddPort_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.
old-location : storage\sm_addport_out.htm
old-project : storage
ms.assetid : e8892d6f-eb82-4262-9105-3c77d8295a3a
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SM_AddPort_OUT, SM_AddPort_OUT, *PSM_AddPort_OUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SM_AddPort_OUT
req.alt-loc : hbapiwmi.h
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
req.typenames : SM_AddPort_OUT, *PSM_AddPort_OUT
---

# _SM_AddPort_OUT structure
The SM_AddPort_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.

## Syntax
````
typedef struct _SM_AddPort_OUT {
  ULONG HBAStatus;
} SM_AddPort_OUT, *PSM_AddPort_OUT;
````

## Members

        
            `HBAStatus`

            The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |