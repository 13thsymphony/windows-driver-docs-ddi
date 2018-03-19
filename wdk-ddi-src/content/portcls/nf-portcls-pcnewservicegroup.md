---
UID: NF:portcls.PcNewServiceGroup
title: PcNewServiceGroup function
author: windows-driver-content
description: The PcNewServiceGroup function creates and initializes a service group.
old-location: audio\pcnewservicegroup.htm
old-project: audio
ms.assetid: 9fcc8cee-61a1-417c-9e69-5c658dab80b2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PcNewServiceGroup, PcNewServiceGroup function [Audio Devices], audio.pcnewservicegroup, audpc-routines_2164b9cd-1bb5-4e51-aa07-6ed9cb40e3fb.xml, portcls/PcNewServiceGroup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewServiceGroup function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcNewServiceGroup
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcNewServiceGroup function
The <b>PcNewServiceGroup</b> function creates and initializes a service group.

## Syntax

````
NTSTATUS PcNewServiceGroup(
  _Out_    PSERVICEGROUP *OutServiceGroup,
  _In_opt_ PUNKNOWN      OuterUnknown
);
````

## Parameters

`OutServiceGroup`

Pointer to the service-group object created by this function. This parameter points to the caller-allocated pointer variable into which the function outputs the pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.

`OuterUnknown`

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


## Return Value

<b>PcNewServiceGroup</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

The <i>OutServiceGroup</i> and <i>OuterUnknown</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcNewServiceGroup function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>