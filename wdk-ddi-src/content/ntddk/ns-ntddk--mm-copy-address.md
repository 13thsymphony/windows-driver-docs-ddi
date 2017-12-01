---
UID: NS.ntddk._MM_COPY_ADDRESS
title: MM_COPY_ADDRESS
author: windows-driver-content
description: The MM_COPY_ADDRESS structure contains either a virtual memory address or a physical memory address.
old-location: kernel\mm_copy_address.htm
old-project: kernel
ms.assetid: 9C9A0D46-587C-43F3-808E-38E81CE3EE50
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: MM_COPY_ADDRESS, MM_COPY_ADDRESS, *PMMCOPY_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MM_COPY_ADDRESS
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# MM_COPY_ADDRESS structure



## -description
<p>The <b>MM_COPY_ADDRESS</b> structure contains either a virtual memory address or a physical memory address.</p>


## -syntax

````
typedef struct _MM_COPY_ADDRESS {
  union {
    PVOID            VirtualAddress;
    PHYSICAL_ADDRESS PhysicalAddress;
  };
} MM_COPY_ADDRESS, *PMM_COPY_ADDRESS;
````


## -struct-fields
<dl>

### -field ( <i>unnamed union</i> )

<dd>
<p>Either a virtual address or a physical address.</p>
<dl>

### -field <b>VirtualAddress</b>

<dd>
<p>A virtual memory address.</p>
</dd>

### -field <b>PhysicalAddress</b>

<dd>
<p>A physical memory address.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="..\ntddk\nf-ntddk-mmcopymemory.md">MmCopyMemory</a> routine.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-mmcopymemory.md">MmCopyMemory</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MM_COPY_ADDRESS structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
