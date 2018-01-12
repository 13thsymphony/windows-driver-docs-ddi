---
UID: NF:wdm.RtlIoEncodeMemIoResource
title: RtlIoEncodeMemIoResource function
author: windows-driver-content
description: The RtlIoEncodeMemIoResource routine updates an IO_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses.
old-location: kernel\rtlioencodememioresource.htm
old-project: kernel
ms.assetid: b2f51d54-3fda-4cbf-a148-0572122ed9fa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIoEncodeMemIoResource
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
req.alt-api: RtlIoEncodeMemIoResource
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlIoEncodeMemIoResource function



## -description
The <b>RtlIoEncodeMemIoResource</b> routine updates an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to describe a range of memory or I/O port addresses.



## -syntax

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


## -parameters

### -param Descriptor [in]

A pointer to the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure to update.


### -param Type [in]

The resource type of the address range. This parameter can be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>. 


### -param Length [in]

The length, in bytes, of the range of assignable addresses. 


### -param Alignment [in]

The alignment, in bytes, of the starting address of address range.


### -param MinimumAddress [in]

The minimum address that can be assigned to the device. 


### -param MaximumAddress [in]

The maximum address that can be assigned to the device.


## -returns
<b>RtlIoEncodeMemIoResource</b> returns an NTSTATUS value. This routine might return one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure was updated.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The specified value for <i>Length</i> or <i>Alignment</i> could not be encoded in an <b>IO_RESOURCE_DESCRIPTOR</b> structure.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One or more of the specified parameters were invalid.

 


## -remarks
Addresses that are larger than 32 bits in length must satisfy certain alignment restrictions, or else the routine returns STATUS_UNSUCCESSFUL.

40 bits

Lowest 8 bits must be zero.

48 bits

Lowest 16 bits must be zero.

64 bits

Lowest 32 bits must be zero.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIoEncodeMemIoResource routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

