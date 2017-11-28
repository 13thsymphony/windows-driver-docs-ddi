---
UID: NS.d3dumddi._D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
title: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up signaling in a call to the pfnSignalSynchronizationObjectCb function.
old-location: display\d3dddicb_signalsynchronizationobject.htm
old-project: display
ms.assetid: 08fbcc15-f40f-46de-b3ff-603bc1476d97
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
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

# D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure



## -description
<p>The D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up signaling in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> function. </p>


## -syntax

````
typedef struct _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT {
  HANDLE               hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
} D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT;
````


## -struct-fields
<dl>

### -field <b>hContext</b>

<dd>
<p>[in] A handle to a Direct3D context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.</p>
</dd>

### -field <b>ObjectCount</b>

<dd>
<p>[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. </p>
</dd>

### -field <b>ObjectHandleArray</b>

<dd>
<p>[in] An array of handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The <b>D3DDDI_MAX_OBJECT_SIGNALED</b> constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544271">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.</p>
</dd>
</dl>

## -remarks


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544271">D3DDDICB_SIGNALFLAGS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
