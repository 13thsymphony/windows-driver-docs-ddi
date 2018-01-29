---
UID : NF:ntddk.KeQueryLogicalProcessorRelationship
title : KeQueryLogicalProcessorRelationship function
author : windows-driver-content
description : The KeQueryLogicalProcessorRelationship routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system.
old-location : kernel\kequerylogicalprocessorrelationship.htm
old-project : kernel
ms.assetid : 343d965d-3e85-423e-a46b-894b19d5df4e
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : KeQueryLogicalProcessorRelationship routine [Kernel-Mode Driver Architecture], kernel.kequerylogicalprocessorrelationship, KeQueryLogicalProcessorRelationship, wdm/KeQueryLogicalProcessorRelationship, k105_0db645b1-dfa2-4d90-856f-975997dc09a8.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h, Wdm.h, Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# KeQueryLogicalProcessorRelationship function
The <b>KeQueryLogicalProcessorRelationship</b> routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system.

## Syntax

````
NTSTATUS KeQueryLogicalProcessorRelationship(
  _In_opt_  PPROCESSOR_NUMBER                        ProcessorNumber,
  _In_      LOGICAL_PROCESSOR_RELATIONSHIP           RelationshipType,
  _Out_opt_ PSYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information,
  _Inout_   PULONG                                   Length
);
````

## Parameters

`ProcessorNumber`

A pointer to a <a href="..\miniport\ns-miniport-_processor_number.md">PROCESSOR_NUMBER</a> structure that identifies the logical processor for which the caller requests relationship information. To request information about <u>all</u> logical processors in the system, set this parameter to <b>NULL</b>.

`RelationshipType`

Specifies the type of relationship information that is requested by the caller. Set this parameter to one of the following <a href="http://go.microsoft.com/fwlink/p/?linkid=155068">LOGICAL_PROCESSOR_RELATIONSHIP</a> enumeration values:
<ul>
<li>
<b>RelationProcessorCore</b>

</li>
<li>
<b>RelationNumaNode</b>

</li>
<li>
<b>RelationCache</b>

</li>
<li>
<b>RelationProcessorPackage</b>

</li>
<li>
<b>RelationGroup</b>

</li>
<li>
<b>RelationAll</b>

</li>
</ul>

`Information`

A pointer to a caller-allocated buffer into which the routine writes an array of one or more <a href="http://go.microsoft.com/fwlink/p/?linkid=155065">SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX</a> structures that contain the information requested by the caller. If the function fails, the contents of this buffer are undefined. Set <i>Information</i> = <b>NULL</b> to obtain the required buffer length before you allocate the buffer. For more information, see the following Remarks section.

`Length`

A pointer to a location that contains the size, in bytes, of the buffer that is pointed to by <i>Information</i>. On entry, *<i>Length</i> contains the size of the caller-allocated buffer that is pointed to by <i>Information</i>. During the call, the routine overwrites the value that is pointed to by <i>Length</i> with the buffer size that is required to contain the requested relationship information.


## Return Value

<b>KeQueryLogicalProcessorRelationship</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>ProcessorNumber</i> parameter points to a PROCESSOR_NUMBER structure that contains invalid information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The caller-allocated buffer that is pointed to by the <i>Information</i> parameter is not large enough to contain the requested relationship information.

</td>
</tr>
</table>

## Remarks

To determine the buffer size to allocate, initially call <b>KeQueryLogicalProcessorRelationship</b> with <i>Information</i> = <b>NULL</b> and *<i>Length</i> = 0. In response, the routine writes the required buffer size to *<i>Length</i> and returns STATUS_INFO_LENGTH_MISMATCH. Next, allocate a buffer of the required size and call <b>KeQueryLogicalProcessorRelationship</b> a second time. In this second call, set <i>Information</i> to the buffer address and *<i>Length</i> to the buffer size. If the second call succeeds, the routine writes the requested relationship information to the buffer and returns STATUS_SUCCESS.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h, Wdm.h, Ntddk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?linkid=155068">LOGICAL_PROCESSOR_RELATIONSHIP</a>

<a href="..\miniport\ns-miniport-_processor_number.md">PROCESSOR_NUMBER</a>

<a href="http://go.microsoft.com/fwlink/p/?linkid=155065">SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryLogicalProcessorRelationship routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>