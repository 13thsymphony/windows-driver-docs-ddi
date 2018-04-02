---
UID: NF:portcls.PcDestroyContent
title: PcDestroyContent function
author: windows-driver-content
description: The PcDestroyContent function deletes a DRM content ID that was created by PcCreateContentMixed. Note that this function call is identical in operation to the DrmDestroyContent function, and its parameter definitions and return value are also identical.
old-location: audio\pcdestroycontent.htm
old-project: audio
ms.assetid: 742ee83c-3db4-4d77-a79d-28bcc405746d
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcDestroyContent, PcDestroyContent function [Audio Devices], audio.pcdestroycontent, audpc-routines_8f5adcf6-89a7-4918-ac2e-78afa45c38c5.xml, portcls/PcDestroyContent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcDestroyContent function in Microsoft Windows XP and later operating systems.
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
-	PcDestroyContent
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcDestroyContent function
The <b>PcDestroyContent</b> function deletes a DRM content ID that was created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff537689">PcCreateContentMixed</a>. Note that this function call is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a> function, and its parameter definitions and return value are also identical.

## Syntax

```
PORTCLASSAPI NTSTATUS PcDestroyContent(
  ULONG ContentId
);
```

## Parameters

`ContentId`

Specifies a nonzero DRM content ID assigned to a KS audio stream by <b>DrmCreateContentMixed</b>. Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.


## Return Value

See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>.

## Remarks

For more information, see the comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcDestroyContent function in Microsoft Windows XP and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537689">PcCreateContentMixed</a>