---
UID: NF:ntifs.RtlCopySid
title: RtlCopySid function
author: windows-driver-content
description: The RtlCopySid routine copies the value of a security identifier (SID) to a buffer.
old-location: ifsk\rtlcopysid.htm
old-project: ifsk
ms.assetid: adfe720f-695e-49a2-b7b5-940ba11bc83f
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.rtlcopysid, RtlCopySid routine [Installable File System Drivers], rtlref_598b8f18-6cd2-4714-a2da-8e91f6aba065.xml, RtlCopySid, ntifs/RtlCopySid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlCopySid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlCopySid function
The <b>RtlCopySid</b> routine copies the value of a security identifier (SID) to a buffer.

## Syntax

````
NTSTATUS RtlCopySid(
  _In_ ULONG DestinationSidLength,
  _In_ PSID  DestinationSid,
  _In_ PSID  SourceSid
);
````

## Parameters

`DestinationSidLength`

Length, in bytes, of the buffer to receive the copy of the SID.

`DestinationSid`

Pointer to a caller-allocated buffer to receive a copy of the source SID structure. The buffer must be at least <b>sizeof</b>(SID),

`SourceSid`

Pointer to the source SID structure to be copied.


## Return Value

<b>RtlCopySid</b> returns STATUS_SUCCESS if the SID was successfully copied. Otherwise, it returns an NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>DestinationSid</i> buffer was not large enough to receive a copy of the SID. 

</td>
</tr>
</table>

## Remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a>



<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlequalsid.md">RtlEqualSid</a>



<a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCopySid routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>