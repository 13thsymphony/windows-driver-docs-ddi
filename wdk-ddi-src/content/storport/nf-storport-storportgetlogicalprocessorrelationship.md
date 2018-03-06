---
UID: NF:storport.StorPortGetLogicalProcessorRelationship
title: StorPortGetLogicalProcessorRelationship function
author: windows-driver-content
description: The StorPortGetLogicalProcessorRelationship routine returns relationship information for one or more specified types.
old-location: storage\storportgetlogicalprocessorrelationship.htm
old-project: storage
ms.assetid: 32b92771-7f23-492c-a3b0-b10032c9f80a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortGetLogicalProcessorRelationship, StorPortGetLogicalProcessorRelationship routine [Storage Devices], storage.storportgetlogicalprocessorrelationship, storport/StorPortGetLogicalProcessorRelationship, storprt_65b00469-41a4-446b-aaa5-fee877aaff3c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortGetLogicalProcessorRelationship
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetLogicalProcessorRelationship function
The <b>StorPortGetLogicalProcessorRelationship</b> routine returns relationship information for one or more specified types. These types include groups, physical packages, and nodes in the host system. The information that is returned includes processor affinity masks that are composed of the logical processors in the host system. These logical processors share the specified relationship types.

## Syntax

````
ULONG StorPortGetLogicalProcessorRelationship(
  _In_     PVOID                                    HwDeviceExtension,
  _In_opt_ PPROCESSOR_NUMBER                        ProcessorNumber,
  _In_     LOGICAL_PROCESSOR_RELATIONSHIP           RelationshipType,
  _Out_    PSYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information,
  _Inout_  PULONG                                   Length
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`ProcessorNumber`

An optional pointer to a processor number for which relationships are to be returned. If this parameter is not provided, information about all processors is returned.

`RelationshipType`

The type of relationship to be returned.

`Information`

A pointer to a buffer that receives the specified information.

`Length`

A pointer to the length of the information buffer, in bytes. Upon return, this value receives the number of bytes that are populated with relationship information.


## Return Value

The <b>StorPortGetLogicalProcessorRelationship</b>routine returns one of the following status codes:

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
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>Information</i> is set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if the supplied buffer is not large enough to hold the requested information.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | StorPortIrql |