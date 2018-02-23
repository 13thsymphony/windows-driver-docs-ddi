---
UID: NS:hbapiwmi._SM_RemovePersistentBinding_OUT
title: "_SM_RemovePersistentBinding_OUT"
author: windows-driver-content
description: The SM_REmovePersistentBinding_OUT structure is used to receive output parameters from the SM_RemovePersistentBinding method.
old-location: storage\sm_removepersistentbinding_out.htm
old-project: storage
ms.assetid: 48d236c4-709d-4a4f-a730-df5f79787fe7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PSM_RemovePersistentBinding_OUT, SM_RemovePersistentBinding_OUT structure [Storage Devices], hbapiwmi/PSM_RemovePersistentBinding_OUT, SM_RemovePersistentBinding_OUT, structs-Fibre_e35eed9b-725a-4d27-90f9-9c40e49e9415.xml, hbapiwmi/SM_RemovePersistentBinding_OUT, PSM_RemovePersistentBinding_OUT structure pointer [Storage Devices], _SM_RemovePersistentBinding_OUT, storage.sm_removepersistentbinding_out, *PSM_RemovePersistentBinding_OUT
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
-	SM_RemovePersistentBinding_OUT
product: Windows
targetos: Windows
req.typenames: SM_RemovePersistentBinding_OUT, *PSM_RemovePersistentBinding_OUT
---

# _SM_RemovePersistentBinding_OUT structure
The SM_REmovePersistentBinding_OUT structure is used to receive output parameters from the SM_RemovePersistentBinding method.

## Syntax
````
typedef struct _SM_RemovePersistentBinding_OUT {
  ULONG HBAStatus;
} SM_RemovePersistentBinding_OUT, *PSM_RemovePersistentBinding_OUT;
````

## Members


`HBAStatus`

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

## Remarks
The WMI tool suite generates a declaration of the SM_RemovePersistentBinding_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |