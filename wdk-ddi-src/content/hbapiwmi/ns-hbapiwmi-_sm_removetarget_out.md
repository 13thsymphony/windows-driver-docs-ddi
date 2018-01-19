---
UID : NS:hbapiwmi._SM_RemoveTarget_OUT
title : _SM_RemoveTarget_OUT
author : windows-driver-content
description : The SM_RemoveTarget_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.
old-location : storage\sm_removetarget_out.htm
old-project : storage
ms.assetid : b93f999e-471a-4f02-a6f2-e21386b9e289
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SM_RemoveTarget_OUT, SM_RemoveTarget_OUT, *PSM_RemoveTarget_OUT
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
req.alt-api : SM_RemoveTarget_OUT
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
req.typenames : SM_RemoveTarget_OUT, *PSM_RemoveTarget_OUT
---

# _SM_RemoveTarget_OUT structure
The SM_RemoveTarget_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.

## Syntax
````
typedef struct _SM_RemoveTarget_OUT {
  ULONG HBAStatus;
} SM_RemoveTarget_OUT, *PSM_RemoveTarget_OUT;
````

## Members

        
            `HBAStatus`

            The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

    ## Remarks
        The WMI tool suite generates a declaration of the SM_RemoveTarget_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |