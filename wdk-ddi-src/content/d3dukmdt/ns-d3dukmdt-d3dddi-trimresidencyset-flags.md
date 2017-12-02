---
UID: NS.d3dukmdt.D3DDDI_TRIMRESIDENCYSET_FLAGS
title: D3DDDI_TRIMRESIDENCYSET_FLAGS
author: windows-driver-content
description: D3DDDI_TRIMRESIDENCYSET_FLAGS is used with pfnTrimResidencySet to trim the residency list for a given device.
old-location: display\d3dddi_trimresidencyset_flags.htm
old-project: display
ms.assetid: B063561B-FA79-44B4-A058-71DB9CBF4804
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDI_TRIMRESIDENCYSET_FLAGS, D3DDDI_TRIMRESIDENCYSET_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_TRIMRESIDENCYSET_FLAGS
req.alt-loc: d3dukmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# D3DDDI_TRIMRESIDENCYSET_FLAGS structure



## -description
<p><b>D3DDDI_TRIMRESIDENCYSET_FLAGS</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-trimresidencyset.md">pfnTrimResidencySet</a> to trim the residency list for a given device.</p>


## -syntax

````
typedef struct D3DDDI_TRIMRESIDENCYSET_FLAGS {
  union {
    struct {
      UINT PeriodicTrim  :1;
      UINT RestartPeriodicTrim  :1;
      UINT TrimToBudget  :1;
      UINT Reserved  :29;
    };
    UINT Value;
  };
} D3DDDI_TRIMRESIDENCYSET_FLAGS;
````


## -struct-fields
<dl>

### -field PeriodicTrim

<dd>
<p>When <b>PeriodicTrim</b> flag is set, the driver is required to performed the following operations:
                                                </p>
<ul>
<li>Trim all allocations that were not referenced since the previous periodic trim request
                                                by comparing the allocation last referenced fence with the last periodic trim context fence.</li>
<li>Refresh the last periodic trim context fence with the last completed context fence.</li>
</ul>
</dd>

### -field RestartPeriodicTrim

<dd>
<p>May not be set together with <b>PeriodicTrim</b> flag.
                                                Reset the last periodic trim context fence to the last completed context fence.</p>
</dd>

### -field TrimToBudget

<dd>
<p>Indicates that the application usage is over the memory budget
                                                and that <b>NumBytesToTrim</b> bytes should be trimmed to fit in the new memory budget.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero.</p>
</dd>

### -field Value

<dd>
<p>The consolidated value of the bit-fields in the structure.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-trimresidencyset.md">pfnTrimResidencySet</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_TRIMRESIDENCYSET_FLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
