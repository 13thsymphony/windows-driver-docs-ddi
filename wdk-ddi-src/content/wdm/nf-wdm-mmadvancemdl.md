---
UID: NF.wdm.MmAdvanceMdl
title: MmAdvanceMdl function
author: windows-driver-content
description: The MmAdvanceMdl routine advances the beginning of an MDL's virtual memory range by the specified number of bytes.
old-location: kernel\mmadvancemdl.htm
old-project: kernel
ms.assetid: 93e84c80-d671-4f04-8532-6c374e1ae72b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: MmAdvanceMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmAdvanceMdl
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# MmAdvanceMdl function



## -description
The <b>MmAdvanceMdl</b> routine advances the beginning of an MDL's virtual memory range by the specified number of bytes.


## -syntax

````
NTSTATUS MmAdvanceMdl(
  _Inout_ PMDLX Mdl,
  _In_    ULONG NumberOfBytes
);
````


## -parameters

### -param Mdl [in, out]

Specifies the MDL to advance.

### -param NumberOfBytes [in]

Specifies the number of bytes to advance the beginning of the MDL.

## -returns
<b>MmAdvanceMdl</b> returns an NTSTATUS code. The possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The routine successfully advanced the beginning of the MDL. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>The caller attempted to advance the beginning of the MDL past the end.

 

## -remarks
<b>MmAdvanceMdl</b> advances only the beginning of the virtual memory address range. The ending address remains the same, and the length of the range is shrunk accordingly.

A higher-level driver can use <b>MmAdvanceMdl</b> under low-memory conditions when a lower-level driver can only partially complete a read/write request. The higher-level driver can use <b>MmAdvanceMdl</b> to advance past the part of the buffer that has already been read or written, and then reissue the IRP to complete the request. (The driver can, of course, repeat this process as many times as necessary.)

If <b>MmAdvanceMdl</b> advances past the initial page, any pages that <b>MmAdvanceMdl</b> passed are immediately unlocked, and the system virtual address that maps the MDL and the user address are also adjusted.

Use of <b>MmAdvanceMdl</b> can slow system performance. It must be used only when all of the following conditions hold:

The higher-level driver, in its own I/O handling, can only complete certain I/O requests after transferring a fixed amount of data, but the lower-level driver only transfers data in smaller amounts. (An example is a network transport driver for the SPX or NBT protocols. Each protocol supports reliable message passing for messages that are bigger than one Ethernet frame. The transport driver can only complete a read request for such a message once it has reassembled the message from multiple Ethernet frames.)

The higher-level driver already tried and failed to allocate a new MDL to transfer a data fragment from an incomplete I/O request. (If the driver succeeds in allocating a new MDL, it must use that MDL and <a href="kernel.iobuildpartialmdl">IoBuildPartialMdl</a> to perform the I/O request instead of <b>MmAdvanceMdl</b>.)

The higher-level driver must continue to make progress, even under low-memory conditions.

Drivers that do not satisfy these conditions must instead use the <b>IoBuildPartialMdl</b> routine to complete any partially-successful I/O operations.

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
Available in Windows XP and later versions of Windows. 
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
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iobuildpartialmdl">IoBuildPartialMdl</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAdvanceMdl routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
