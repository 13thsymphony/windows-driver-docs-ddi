---
UID: NF:portcls.IDrmPort2.AddContentHandlers
title: IDrmPort2::AddContentHandlers method
author: windows-driver-content
description: The AddContentHandlers method provides the system with a list of functions that handle protected content.
old-location: audio\idrmport2_addcontenthandlers.htm
old-project: audio
ms.assetid: b65608f4-de9a-4bed-a966-586e50c50e45
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: AddContentHandlers method [Audio Devices], AddContentHandlers method [Audio Devices], IDrmPort2 interface, AddContentHandlers,IDrmPort2.AddContentHandlers, IDrmPort2, IDrmPort2 interface [Audio Devices], AddContentHandlers method, IDrmPort2::AddContentHandlers, audio.idrmport2_addcontenthandlers, audmp-routines_f2bbb2e7-eed1-4ffd-93d9-050dcb6b0b60.xml, portcls/IDrmPort2::AddContentHandlers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IDrmPort2.AddContentHandlers
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IDrmPort2::AddContentHandlers method
The <code>AddContentHandlers</code> method provides the system with a list of functions that handle protected content. Note that this method is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a> function, and its parameter definitions and return value are also identical.

## Syntax

```
NTSTATUS AddContentHandlers(
  ULONG ContentId,
  PVOID *paHandlers,
  ULONG NumHandlers
);
```

## Parameters

`ContentId`



`paHandlers`



`NumHandlers`




## Return Value

See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>.

## Remarks

See comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536573">IDrmPort2</a>