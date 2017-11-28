---
UID: NS.d3dkmthk._D3DKMT_MULTISAMPLEMETHOD
title: D3DKMT_MULTISAMPLEMETHOD
author: windows-driver-content
description: The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.
old-location: display\d3dkmt_multisamplemethod.htm
old-project: display
ms.assetid: 6cdc0665-61e6-4c13-9b15-46ce301febec
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_MULTISAMPLEMETHOD, D3DKMT_MULTISAMPLEMETHOD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_MULTISAMPLEMETHOD
req.alt-loc: d3dkmthk.h
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

# D3DKMT_MULTISAMPLEMETHOD structure



## -description
<p>The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.</p>


## -syntax

````
typedef struct _D3DKMT_MULTISAMPLEMETHOD {
  UINT NumSamples;
  UINT NumQualityLevels;
  UINT Reserved;
} D3DKMT_MULTISAMPLEMETHOD;
````


## -struct-fields
<dl>

### -field <b>NumSamples</b>

<dd>
<p>[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).</p>
</dd>

### -field <b>NumQualityLevels</b>

<dd>
<p>[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range extends from zero through the reported maximum quality setting.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>[out] Reserved.</p>
</dd>
</dl>

## -remarks
<p>The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires, with the condition that each incremental step noticeably improves the quality of the presented image.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548039">D3DKMT_GETMULTISAMPLEMETHODLIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546975">D3DKMTGetMultisampleMethodList</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_MULTISAMPLEMETHOD structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
