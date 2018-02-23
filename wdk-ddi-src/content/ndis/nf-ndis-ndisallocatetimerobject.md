---
UID: NF:ndis.NdisAllocateTimerObject
title: NdisAllocateTimerObject function
author: windows-driver-content
description: The NdisAllocateTimerObject function allocates and initializes a timer object for use with subsequent NdisXxx timer functions.
old-location: netvista\ndisallocatetimerobject.htm
old-project: netvista
ms.assetid: feb5e4cf-7e23-434e-9dc5-bb445a6f5606
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisAllocateTimerObject function [Network Drivers Starting with Windows Vista], netvista.ndisallocatetimerobject, NdisAllocateTimerObject, ndis_timer_ref_38e524b5-9210-4c60-b9ea-66fc23593dad.xml, ndis/NdisAllocateTimerObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Timer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateTimerObject
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisAllocateTimerObject function
The 
  <b>NdisAllocateTimerObject</b> function allocates and initializes a timer object for use with subsequent 
  <b>Ndis<i>Xxx</i></b> timer functions.

## Syntax

````
NDIS_STATUS NdisAllocateTimerObject(
  _In_  NDIS_HANDLE                 NdisHandle,
  _In_  PNDIS_TIMER_CHARACTERISTICS TimerCharacteristics,
  _Out_ PNDIS_HANDLE                pTimerObject
);
````

## Parameters

`NdisHandle`

An NDIS handle that was obtained during caller initialization. For more information about
     obtaining NDIS handles, see 
     <a href="https://msdn.microsoft.com/752b0d64-2ca3-4dc0-a6cd-642e96af1f8f">Obtaining Pool Handles</a>.

`TimerCharacteristics`

A pointer to a caller-supplied 
     <a href="..\ndis\ns-ndis-_ndis_timer_characteristics.md">
     NDIS_TIMER_CHARACTERISTICS</a> structure that specifies the characteristics of the allocated timer
     object.

`pTimerObject`

A pointer to an NDIS timer object handle that NDIS provides to identify the timer object in
     subsequent calls to 
     <b>Ndis<i>Xxx</i></b> timer functions.


## Return Value

<b>NdisAllocateTimerObject</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The timer object was allocated successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
The allocation failed because the information in the NDIS_TIMER_CHARACTERISTICS structure is
       invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
None of the preceding status values apply.

</td>
</tr>
</table>

## Remarks

To use timer services, an NDIS driver first calls the 
    <b>NdisAllocateTimerObject</b> function to initialize a timer object. Typically, 
    <b>NdisAllocateTimerObject</b> is called during driver initialization.

To start a timer, call the 
    <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function. Calls to 
    <b>NdisSetTimerObject</b> insert the timer object in the system timer queue. Only one instance of a
    particular timer object can be queued at any given moment.

To cancel a timer, call the 
    <a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a> function. 
    <b>NdisCancelTimerObject</b> dequeues the timer object if it is currently queued.

To free a timer object, you must call the 
    <a href="..\ndis\nf-ndis-ndisfreetimerobject.md">NdisFreeTimerObject</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Timer_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisfreetimerobject.md">NdisFreeTimerObject</a>



<a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a>



<a href="..\ndis\ns-ndis-_ndis_timer_characteristics.md">NDIS_TIMER_CHARACTERISTICS</a>



<a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a>



<a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateTimerObject function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>