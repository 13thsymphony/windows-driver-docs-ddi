---
UID: NC.d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB
author: windows-driver-content
description: The pfnSignalSynchronizationObjectCb function inserts a signal on the specified synchronization objects in the specified context DMA stream.
old-location: display\pfnsignalsynchronizationobjectcb.htm
old-project: display
ms.assetid: 12ffa230-2c26-4cd3-ae83-f753a0b6ba38
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnSignalSynchronizationObjectCb
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB callback



## -description
<p>The <b>pfnSignalSynchronizationObjectCb</b> function inserts a signal on the specified synchronization objects in the specified context DMA stream. </p>


## -prototype

````
PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB pfnSignalSynchronizationObjectCb;

__checkResult HRESULT APIENTRY CALLBACK pfnSignalSynchronizationObjectCb(
  _In_       HANDLE                               hDevice,
  _In_ const D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p>A handle to a display device (that is, the graphics context).</p>
</dd>

### -param <i>pData</i> [in]

<dd>
<p>A pointer to a <a href="..\d3dumddi\ns-d3dumddi--d3dddicb-signalsynchronizationobject.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a> structure that describes the synchronization objects and context DMA stream that signaling is set up on. </p>
</dd>
</dl>

## -returns
<p><b>pfnSignalSynchronizationObjectCb</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The signaling was successfully set up.</p><dl>
<dt><b>E_INVALIDARG</b></dt>
</dl><p>Parameters were validated and determined to be incorrect.</p>

<p> </p>

<p>This function might also return other HRESULT values.</p>

## -remarks
<p>
<p><b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSignalSynchronizationObjectCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.</p>
</p>

<p><b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSignalSynchronizationObjectCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.</p>

<p>The following code example shows how to insert a signal on synchronization objects.</p>

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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddicb-signalsynchronizationobject.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
