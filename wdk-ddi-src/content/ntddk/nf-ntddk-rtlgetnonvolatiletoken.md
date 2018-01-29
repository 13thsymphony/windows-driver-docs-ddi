---
UID : NF:ntddk.RtlGetNonVolatileToken
title : RtlGetNonVolatileToken function
author : windows-driver-content
description : The routine, RtlGetNonVolatileToken, gets various properties about a non-volatile memory buffer and stores them in the variable NvToken.
old-location : ifsk\rtlgetnonvolatiletoken.htm
old-project : ifsk
ms.assetid : A9E866D4-C47F-4926-A838-EDB739CF1185
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlGetNonVolatileToken routine [Installable File System Drivers], RtlGetNonVolatileToken, ntddk/RtlGetNonVolatileToken, ifsk.rtlgetnonvolatiletoken
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Winnt.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1703
req.target-min-winversvr : None supported
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# RtlGetNonVolatileToken function
The routine, <b>RtlGetNonVolatileToken</b>, gets various properties about a non-volatile memory
    buffer and stores them in the variable <b>NvToken</b>.

## Syntax

````
NTSTATUS RtlGetNonVolatileToken(
   _In_reads_bytes_(Size) PVOID NvBuffer,
   _In_ SIZE_T                  Size,
   _Outptr_ PVOID               *NvToken
);
````

## Parameters

`NvBuffer`

A pointer to the non-volatile memory that the returned <b>NvToken</b> is going to track state for. This should be an address obtained from a file mapping object.

`Size`

The length, in bytes, of the non-volatile memory buffer <b>NvBuffer</b> points to.

`NvToken`

A pointer to an opaque structure that tracks
        information about the given non-volatile memory region which <b>RtlGetNonVolatileToken</b> had returned.


## Return Value

The routine <b>RtlGetNonVolatileToken</b> returns one of the status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller had insufficient access rights to perform the requested action.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH
</b></dt>
</dl>
</td>
<td width="60%">
The specified base address is outside the range of accessible addresses.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <b>NvBuffer</b> is not the same length as specified in<b>Size</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful.

</td>
</tr>
</table>

## Remarks

This routine is currently not supported for Windows Server until the next major release of Windows Server.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Winnt.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="ifsk.RtlFlushNonVolatileMemory" tabindex="0"><b>
RtlFlushNonVolatileMemory</b></mshelp:link>

<a href="https://msdn.microsoft.com/49DDDEF8-F949-4674-A18B-9BB091D163C2">RtlWriteNonVolatileMemory</a>

<a href="https://msdn.microsoft.com/169C5F41-B372-4056-AAC5-53DD0582A563">RtlFlushNonVolatileMemoryRanges</a>

<a href="https://msdn.microsoft.com/EA1C2DF3-591C-407A-ABBF-DE615466A498">RtlDrainNonVolatileFlush</a>

<a href="https://msdn.microsoft.com/8E083814-7408-47D2-A811-2DCBDCD13097">RtlFreeNonVolatileToken</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetNonVolatileToken routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>