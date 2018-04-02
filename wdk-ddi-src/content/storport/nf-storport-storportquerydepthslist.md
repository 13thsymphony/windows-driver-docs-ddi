---
UID: NF:storport.StorPortQueryDepthSList
title: StorPortQueryDepthSList function
author: windows-driver-content
description: Retrieves the number of entries in a Storport managed singly linked list.
old-location: storage\storportquerydepthslist.htm
old-project: storage
ms.assetid: 5E1CE999-8173-49B6-8CF7-F3A5B193A230
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortQueryDepthSList, StorPortQueryDepthSList routine [Storage Devices], storage.storportquerydepthslist, storport/StorPortQueryDepthSList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortQueryDepthSList
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortQueryDepthSList function
Retrieves the number of entries in a Storport managed singly linked list.

## Syntax

```
ULONG StorPortQueryDepthSList(
  PVOID              HwDeviceExtension,
  PSTOR_SLIST_HEADER SListHead,
  PSHORT             Result
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`SListHead`

A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.

`Result`

A pointer to a <b>SHORT</b> value which receives the  list depth count.


## Return Value

<b>StorPortQueryDepthSList</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list depth  was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>SListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>

## Remarks

Since <b>StorPortQueryDepthSList</b> is not interlocked, the list  depth value pointed to by <i>Result</i> on return is not reliable in when multiple threads are operating on the list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh967735">StorPortInitializeSListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967736">StorPortInterlockedFlushSList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967737">StorPortInterlockedPopEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967738">StorPortInterlockedPushEntrySList</a>