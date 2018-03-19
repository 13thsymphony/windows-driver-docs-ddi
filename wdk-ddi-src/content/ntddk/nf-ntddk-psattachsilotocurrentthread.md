---
UID: NF:ntddk.PsAttachSiloToCurrentThread
title: PsAttachSiloToCurrentThread function
author: windows-driver-content
description: This routine places a thread temporarily into the specified Silo.
old-location: kernel\psattachsilotocurrentthread.htm
old-project: kernel
ms.assetid: 1C66E50F-3BD7-4038-9FDF-2F2B712D9B5E
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsAttachSiloToCurrentThread, PsAttachSiloToCurrentThread routine [Kernel-Mode Driver Architecture], kernel.psattachsilotocurrentthread, ntddk/PsAttachSiloToCurrentThread
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
-	PsAttachSiloToCurrentThread
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsAttachSiloToCurrentThread function
This routine places a thread temporarily into the specified <i>Silo</i>.

## Syntax

````
PESILO PsAttachSiloToCurrentThread(
  _In_ PESILO Silo
);
````

## Parameters

`Silo`

The silo that the thread is to impersonate. The caller must hold a  reference to the silo throughout the duration of the impersonation.


## Return Value

The previous silo that was attached to the current thread.

## Remarks

The specified <i>Silo</i> is attached to the current thread so that it becomes the effective silo for the thread.

The thread then operates within the namespace of the attached silo until <a href="..\ntddk\nf-ntddk-psdetachsilofromcurrentthread.md">PsDetachSiloFromCurrentThread</a> is called.


#### Examples

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>PESILO PreviousSilo = PsAttachSiloToCurrentThread();

// Do work within the silo context

PsDetachSiloFromCurrentThread(PreviousSilo);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |

## See Also

<a href="..\ntddk\nf-ntddk-psdetachsilofromcurrentthread.md">PsDetachSiloFromCurrentThread</a>