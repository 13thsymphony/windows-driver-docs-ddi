---
UID: NF:wdm.RtlIoEncodeMemIoResource
title: RtlIoEncodeMemIoResource function
author: windows-driver-content
description: The RtlIoEncodeMemIoResource routine updates an IO_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses.
old-location: kernel\rtlioencodememioresource.htm
old-project: kernel
ms.assetid: b2f51d54-3fda-4cbf-a148-0572122ed9fa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlIoEncodeMemIoResource, RtlIoEncodeMemIoResource routine [Kernel-Mode Driver Architecture], k109_2e51e72a-98c4-4600-8e9c-41251c3e9849.xml, kernel.rtlioencodememioresource, wdm/RtlIoEncodeMemIoResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIoEncodeMemIoResource
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlIoEncodeMemIoResource function
The <b>RtlIoEncodeMemIoResource</b> routine updates an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to describe a range of memory or I/O port addresses.

## Syntax

````
NTSTATUS RtlIoEncodeMemIoResource(
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor,
  _In_ UCHAR                   Type,
  _In_ ULONGLONG               Length,
  _In_ ULONGLONG               Alignment,
  _In_ ULONGLONG               MinimumAddress,
  _In_ ULONGLONG               MaximumAddress
);
````

## Parameters

`Descriptor`

A pointer to the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to update.

`Type`

The resource type of the address range. This parameter can be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>.

`Length`

The length, in bytes, of the range of assignable addresses.

`Alignment`

The alignment, in bytes, of the starting address of address range.

`MinimumAddress`

The minimum address that can be assigned to the device.

`MaximumAddress`

The maximum address that can be assigned to the device.


## Return Value

<b>RtlIoEncodeMemIoResource</b> returns an NTSTATUS value. This routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure was updated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified value for <i>Length</i> or <i>Alignment</i> could not be encoded in an <b>IO_RESOURCE_DESCRIPTOR</b> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One or more of the specified parameters were invalid.

</td>
</tr>
</table>

## Remarks

Addresses that are larger than 32 bits in length must satisfy certain alignment restrictions, or else the routine returns STATUS_UNSUCCESSFUL.

<table>
<tr>
<th>Address length</th>
<th>Alignment restriction</th>
</tr>
<tr>
<td>
40 bits

</td>
<td>
Lowest 8 bits must be zero.

</td>
</tr>
<tr>
<td>
48 bits

</td>
<td>
Lowest 16 bits must be zero.

</td>
</tr>
<tr>
<td>
64 bits

</td>
<td>
Lowest 32 bits must be zero.

</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



<a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIoEncodeMemIoResource routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>