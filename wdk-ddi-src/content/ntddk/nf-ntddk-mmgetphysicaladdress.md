---
UID: NF:ntddk.MmGetPhysicalAddress
title: MmGetPhysicalAddress function
author: windows-driver-content
description: The MmGetPhysicalAddress routine returns the physical address corresponding to a valid nonpaged virtual address.
old-location: kernel\mmgetphysicaladdress.htm
old-project: kernel
ms.assetid: 2381c1c2-d7fc-4cb2-bbdf-2a95c78c34d0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmGetPhysicalAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmGetPhysicalAddress
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
req.irql: Any level (see Remarks section)
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# MmGetPhysicalAddress function



## -description
The <b>MmGetPhysicalAddress</b> routine returns the physical address corresponding to a valid nonpaged virtual address.



## -syntax

````
PHYSICAL_ADDRESS MmGetPhysicalAddress(
  _In_ PVOID BaseAddress
);
````


## -parameters

### -param BaseAddress [in]

Pointer to the virtual address for which to return the physical address. 


## -returns
<b>MmGetPhysicalAddress</b> returns the physical address that corresponds to the given virtual address.

Do not use this routine to obtain physical addresses for use with DMA operations. For information about the proper techniques for performing DMA operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540519">Adapter Objects and DMA</a>.


## -remarks
Callers of <b>MmGetPhysicalAddress</b> can be running at any IRQL, provided that the <i>BaseAddress</i> value is valid.


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
<dt>Ntddk.h (include Ntddk.h)</dt>
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
Any level (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-mmisaddressvalid.md">MmIsAddressValid</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554588">MmIsNonPagedSystemAddressValid</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmGetPhysicalAddress routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

