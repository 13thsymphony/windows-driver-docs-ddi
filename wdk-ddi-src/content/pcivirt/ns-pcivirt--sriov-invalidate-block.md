---
UID: NS.pcivirt._SRIOV_INVALIDATE_BLOCK
title: SRIOV_INVALIDATE_BLOCK
author: windows-driver-content
description: Contains the configuration block information. This structure is used in a IOCTL_SRIOV_INVALIDATE_BLOCK request.
old-location: pci\sriov_invalidate_block.htm
old-project: PCI
ms.assetid: 483e6144-9752-4d47-9ed4-7e73bc0a59cc
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SRIOV_INVALIDATE_BLOCK, SRIOV_INVALIDATE_BLOCK, *PSRIOV_INVALIDATE_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRIOV_INVALIDATE_BLOCK
req.alt-loc: Pcivirt.h
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

# SRIOV_INVALIDATE_BLOCK structure



## -description
<p>Contains the configuration block information. This structure is used in a <a href="buses.ioctl_sriov_invalidate_block">IOCTL_SRIOV_INVALIDATE_BLOCK</a> request.</p>


## -syntax

````
typedef struct _SRIOV_INVALIDATE_BLOCK {
  USHORT  VfIndex;
  UINT64  BlockMask;
} SRIOV_INVALIDATE_BLOCK, SRIOV_INVALIDATE_BLOCK;
````


## -struct-fields
<dl>

### -field <b>VfIndex</b>

<dd>
<p>Zero-based index of the virtual function (VF) from the first VF exposed by this physical function (PF).</p>
</dd>

### -field <b>BlockMask</b>

<dd>
<p>a block of configuration data.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ioctl_sriov_invalidate_block">IOCTL_SRIOV_INVALIDATE_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20SRIOV_INVALIDATE_BLOCK structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
