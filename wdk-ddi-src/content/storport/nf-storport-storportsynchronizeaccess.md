---
UID: NF:storport.StorPortSynchronizeAccess
title: StorPortSynchronizeAccess function
author: windows-driver-content
description: The StorPortSynchronizeAccess routine provides synchronized access to a miniport driver's device extension.
old-location: storage\storportsynchronizeaccess.htm
old-project: storage
ms.assetid: eece67ed-faff-4166-8fa0-d501df9c1363
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortSynchronizeAccess, StorPortSynchronizeAccess routine [Storage Devices], storage.storportsynchronizeaccess, storport/StorPortSynchronizeAccess, storprt_25ee1679-940a-4758-9828-123a9ad24268.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortSynchronizeAccess
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortSynchronizeAccess function
The <b>StorPortSynchronizeAccess</b> routine provides synchronized access to a miniport driver's device extension.

## Syntax

```
STORPORT_API BOOLEAN StorPortSynchronizeAccess(
  PVOID                     HwDeviceExtension,
  PSTOR_SYNCHRONIZED_ACCESS SynchronizedAccessRoutine,
  PVOID                     Context
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`SynchronizedAccessRoutine`

Pointer to a caller-supplied routine whose execution is to be synchronized with the execution of the ISR associated with the interrupt objects. For a prototype of this routine, see the Remarks section later in this topic.

`Context`

Pointer to a context area to be passed to the caller-supplied callback routine when it is called.


## Return Value

The return value from  <i>SynchronizedAccessRoutine</i>.

## Remarks

Miniport drivers that operate in full-duplex mode, and that access information that is shared between their <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> routine and interrupt-service routine, must use this routine to access the shared data in a synchronized manner. 

The miniport driver passes a callback routine to <b>StorPortSynchronizeAccess</b>, and <b>StorPortSynchronizeAccess</b> calls it after guaranteeing exclusive access to sensitive data structures. The miniport driver's callback routine must conform to the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
(* PSTOR_SYNCHRONIZED_ACCESS) (
  IN PVOID HwDeviceExtension,
 IN PVOID Context
  );</pre>
</td>
</tr>
</table></span></div>
where <i>HwDeviceExtension</i> is a pointer to the hardware device extension, and <i>Context</i> is just a pointer to the same context information that the caller supplied when calling <b>StorPortSynchronizeAccess</b>. 

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/storage/synchronized-access-within-unsynchronized-miniport-driver-routines">Synchronized Access within Unsynchronized Miniport Driver Routines</a>.

For more information about synchronization routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553302">KeSynchronizeExecution</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553302">KeSynchronizeExecution</a>