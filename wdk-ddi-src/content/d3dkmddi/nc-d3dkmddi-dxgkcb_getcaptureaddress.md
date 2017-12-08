---
UID: NC.d3dkmddi.DXGKCB_GETCAPTUREADDRESS
title: DXGKCB_GETCAPTUREADDRESS
author: windows-driver-content
description: The DxgkCbGetCaptureAddress function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.
old-location: display\dxgkcbgetcaptureaddress.htm
old-project: display
ms.assetid: f87a5a5f-20d3-48cb-93f0-114eafe7238b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbGetCaptureAddress
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: < DISPATCH_LEVEL
---

# DXGKCB_GETCAPTUREADDRESS callback



## -description
The <b>DxgkCbGetCaptureAddress</b> function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.


## -prototype

````
DXGKCB_GETCAPTUREADDRESS DxgkCbGetCaptureAddress;

NTSTATUS APIENTRY DxgkCbGetCaptureAddress(
  _Inout_ DXGKARGCB_GETCAPTUREADDRESS *pData
)
{ ... }
````


## -parameters

### -param pData [in, out]

[in/out] A pointer to a <a href="display.dxgkargcb_getcaptureaddress">DXGKARGCB_GETCAPTUREADDRESS</a> structure that describes parameters for retrieving information about a capture buffer.

## -returns
<b>DxgkCbGetCaptureAddress</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><b>DxgkCbGetCaptureAddress</b> successfully retrieved the capture buffer information.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The allocation handle that is specified in the <b>hAllocation</b> member of the <a href="display.dxgkargcb_getcaptureaddress">DXGKARGCB_GETCAPTUREADDRESS</a> structure that the <i>pData</i> parameter pointed to was either invalid or did not represent a capture buffer. 

 

<i>DxgkCbGetCaptureAddress</i> might also return other error codes that are defined in Ntstatus.h.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkargcb_getcaptureaddress">DXGKARGCB_GETCAPTUREADDRESS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_GETCAPTUREADDRESS callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
