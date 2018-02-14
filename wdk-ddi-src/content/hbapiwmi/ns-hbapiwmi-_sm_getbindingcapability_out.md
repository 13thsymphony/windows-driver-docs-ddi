---
UID: NS:hbapiwmi._SM_GetBindingCapability_OUT
title: "_SM_GetBindingCapability_OUT"
author: windows-driver-content
description: The SM_GetBindingCapability_OUT structure is used to receive output parameters from the SM_GetBindingCapability method.
old-location: storage\sm_getbindingcapability_out.htm
old-project: storage
ms.assetid: 7dfa36be-ab05-478d-b47a-783e599545bf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SM_GetBindingCapability_OUT, storage.sm_getbindingcapability_out, _SM_GetBindingCapability_OUT, SM_GetBindingCapability_OUT structure [Storage Devices], structs-Fibre_00260060-51c3-4d04-94a2-bad7903f0e6e.xml, hbapiwmi/PSM_GetBindingCapability_OUT, PSM_GetBindingCapability_OUT, *PSM_GetBindingCapability_OUT, PSM_GetBindingCapability_OUT structure pointer [Storage Devices], hbapiwmi/SM_GetBindingCapability_OUT
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
-	SM_GetBindingCapability_OUT
product: Windows
targetos: Windows
req.typenames: "*PSM_GetBindingCapability_OUT, SM_GetBindingCapability_OUT"
---

# _SM_GetBindingCapability_OUT structure
The SM_GetBindingCapability_OUT structure is used to receive output parameters from the SM_GetBindingCapability method.

## Syntax
````
typedef struct _SM_GetBindingCapability_OUT {
  ULONG HBAStatus;
  ULONG Flags;
} SM_GetBindingCapability_OUT, *PSM_GetBindingCapability_OUT;
````

## Members


`Flags`

The HBA_BIND_CAPABILITY binding capabilities.

`HBAStatus`

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

## Remarks
The WMI tool suite generates a declaration of the SM_GetBindingCapability_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |