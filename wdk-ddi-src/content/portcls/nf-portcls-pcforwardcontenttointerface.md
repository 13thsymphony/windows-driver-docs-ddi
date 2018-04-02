---
UID: NF:portcls.PcForwardContentToInterface
title: PcForwardContentToInterface function
author: windows-driver-content
description: The PcForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content.
old-location: audio\pcforwardcontenttointerface.htm
old-project: audio
ms.assetid: 5aa6aa90-ef41-467e-a096-5ab660b3f357
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcForwardContentToInterface, PcForwardContentToInterface function [Audio Devices], audio.pcforwardcontenttointerface, audpc-routines_1c3b8e8d-556e-4029-9e25-5a2e083dd17f.xml, portcls/PcForwardContentToInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardContentToInterface function in Microsoft Windows XP and later operating systems.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcForwardContentToInterface
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcForwardContentToInterface function
The <b>PcForwardContentToInterface</b> function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. Note that this function call is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a> function, and its parameter definitions and return value are also identical.

## Syntax

```
PORTCLASSAPI NTSTATUS PcForwardContentToInterface(
  ULONG    ContentId,
  PUNKNOWN pUnknown,
  ULONG    NumMethods
);
```

## Parameters

`ContentId`

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.

`pUnknown`

Pointer to a COM interface that directly receives KS audio stream data for a KS audio filter.

`NumMethods`

Specifies the total number of methods in the COM interface that <i>pUnknown</i> points to, including all the methods in its base interfaces.


## Return Value

See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>.

## Remarks

For more information, see the comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcForwardContentToInterface function in Microsoft Windows XP and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>