---
UID: NF.wdm.RtlUshortByteSwap
title: RtlUshortByteSwap function
author: windows-driver-content
description: The RtlUshortByteSwap routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.
old-location: kernel\rtlushortbyteswap.htm
old-project: kernel
ms.assetid: 83f6a599-0b35-4a02-b20f-80abcc6eae4f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlUshortByteSwap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlUshortByteSwap
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
req.product: Windows 10 or later.
---

# RtlUshortByteSwap function



## -description
The <b>RtlUshortByteSwap</b> routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.



## -syntax

````
USHORT RtlUshortByteSwap(
  _In_ USHORT Source
);
````


## -parameters

### -param Source [in]

A USHORT value to convert to a byte-swapped version.


## -returns
The byte-swapped version of the <i>Source</i> input parameter value.


## -remarks
For example, if the <i>Source</i> parameter value is 0x1234, the routine returns 0x3412.

A typical use of this routine is to convert a USHORT value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohs</b> or <b>htons</b>.

To reverse the ordering of bytes in a ULONG value, use the <a href="kernel.rtlulongbyteswap">RtlUlongByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="kernel.rtlulonglongbyteswap">RtlUlonglongByteSwap</a> routine.


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
Available starting with Windows 2000.

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
<a href="kernel.rtlulongbyteswap">RtlUlongByteSwap</a>
</dt>
<dt>
<a href="kernel.rtlulonglongbyteswap">RtlUlonglongByteSwap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUshortByteSwap routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

