---
UID: NS:hbapiwmi._SM_RemoveTarget_OUT
title: "_SM_RemoveTarget_OUT"
author: windows-driver-content
description: The SM_RemoveTarget_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.
old-location: storage\sm_removetarget_out.htm
old-project: storage
ms.assetid: b93f999e-471a-4f02-a6f2-e21386b9e289
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PSM_RemoveTarget_OUT structure pointer [Storage Devices], _SM_RemoveTarget_OUT, SM_RemoveTarget_OUT, PSM_RemoveTarget_OUT, storage.sm_removetarget_out, hbapiwmi/PSM_RemoveTarget_OUT, hbapiwmi/SM_RemoveTarget_OUT, *PSM_RemoveTarget_OUT, structs-Fibre_3535f161-920f-4483-80d0-3d2d9863c935.xml, SM_RemoveTarget_OUT structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SM_RemoveTarget_OUT
product: Windows
targetos: Windows
req.typenames: SM_RemoveTarget_OUT, *PSM_RemoveTarget_OUT
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
The WMI tool suite generates a declaration of the SM_RemoveTarget_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |