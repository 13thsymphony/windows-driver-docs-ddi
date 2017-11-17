---
UID: NC.d3dkmddi.DXGKCB_ENUMHANDLECHILDREN
title: DXGKCB_ENUMHANDLECHILDREN
author: windows-driver-content
description: The DxgkCbEnumHandleChildren function enumerates all of the allocations that are associated with a given resource, one allocation at a time.
old-location: display\dxgkcbenumhandlechildren.htm
ms.assetid: 36307e63-9e94-4441-92c6-fd4293ea8fa9
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbEnumHandleChildren
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
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
req.iface: 
---

# DXGKCB_ENUMHANDLECHILDREN callback



## -description
<p>The <b>DxgkCbEnumHandleChildren</b> function enumerates all of the allocations that are associated with a given resource, one allocation at a time.</p>


## -prototype

````
DXGKCB_ENUMHANDLECHILDREN DxgkCbEnumHandleChildren;

D3DKMT_HANDLE APIENTRY DxgkCbEnumHandleChildren(
  _In_ const DXGKARGCB_ENUMHANDLECHILDREN *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>pData</i> [in]

<dd>
<p>[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure that describes the parent resource and the index of the child allocation to retrieve.</p>
</dd>
</dl>

## -returns
<p><i>DxgkCbEnumHandleChildren</i> returns the graphics subsystem-specific handle to the child allocation that the <i>pData</i> parameter describes. To retrieve the device-specific data for the handle, the display miniport driver must call the <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function.</p>

<p><i>DxgkCbEnumHandleChildren</i> returns a <b>NULL</b> handle if the child-allocation index that the <b>Index</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure supplies exceeds the number of allocations that are associated with the parent resource. If <i>DxgkCbEnumHandleChildren</i> unexpectedly returns a <b>NULL</b> handle, the Microsoft DirectX graphics kernel subsystem was unable to resolve the handle to the parent resource because, for example, of the following possible reasons:</p>

<p>If a <b>NULL</b> handle is returned unexpectedly, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.</p>

## -remarks
<p>The display miniport driver can call the <b>DxgkCbEnumHandleChildren</b> function in a loop to enumerate all of the allocations that are associated with a resource. If the display miniport driver sets the <b>Index</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure that is pointed to by the <i>pData</i> parameter to 0, <b>DxgkCbEnumHandleChildren</b> returns the first allocation handle; if <b>Index</b> is set to 1, <b>DxgkCbEnumHandleChildren</b> returns the second allocation handle; and so on. If <b>Index</b> is greater than the number of allocations that are associated with the resource, <b>DxgkCbEnumHandleChildren</b> returns <b>NULL</b>. </p>

<p>The display miniport driver can call the <b>DxgkCbEnumHandleChildren</b> function in a loop to enumerate all of the allocations that are associated with a resource. If the display miniport driver sets the <b>Index</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a> structure that is pointed to by the <i>pData</i> parameter to 0, <b>DxgkCbEnumHandleChildren</b> returns the first allocation handle; if <b>Index</b> is set to 1, <b>DxgkCbEnumHandleChildren</b> returns the second allocation handle; and so on. If <b>Index</b> is greater than the number of allocations that are associated with the resource, <b>DxgkCbEnumHandleChildren</b> returns <b>NULL</b>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557528">DXGKARGCB_ENUMHANDLECHILDREN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_ENUMHANDLECHILDREN callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
