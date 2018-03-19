---
UID: NF:ntddk.PsDetachSiloFromCurrentThread
title: PsDetachSiloFromCurrentThread function
author: windows-driver-content
description: This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the PsAttachSiloToCurrentThread routine.
old-location: kernel\psdetachsilofromcurrentthread.htm
old-project: kernel
ms.assetid: E364130B-9709-4FD9-8654-9FBC52E29145
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsDetachSiloFromCurrentThread, PsDetachSiloFromCurrentThread routine [Kernel-Mode Driver Architecture], kernel.psdetachsilofromcurrentthread, ntddk/PsDetachSiloFromCurrentThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsDetachSiloFromCurrentThread
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsDetachSiloFromCurrentThread function
This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the  <a href="..\ntddk\nf-ntddk-psattachsilotocurrentthread.md">PsAttachSiloToCurrentThread</a> routine.



<div class="alert"><b>Note</b>  The caller is responsible for dereferencing the object after the detach has completed.</div>
<div> </div>

## Syntax

````
void PsDetachSiloFromCurrentThread(
  _In_ PESILO PreviousSilo
);
````

## Parameters

`PreviousSilo`

The value returned from the silo attach call.


## Return Value

This routine does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |

## See Also

<a href="..\ntddk\nf-ntddk-psattachsilotocurrentthread.md">PsAttachSiloToCurrentThread</a>