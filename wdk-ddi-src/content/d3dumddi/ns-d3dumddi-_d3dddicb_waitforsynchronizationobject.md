---
UID: NS.D3DUMDDI._D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
title: _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up the wait in a call to the pfnWaitForSynchronizationObjectCb function.
old-location: display\d3dddicb_waitforsynchronizationobject.htm
old-project: display
ms.assetid: 8f235fc4-924b-4cc4-858d-5009e69fae47
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
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
req.alt-api: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
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
---

# _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure



## -description
The D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up the wait in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a> function. 


## -syntax

````
typedef struct _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT {
  HANDLE        hContext;
  UINT          ObjectCount;
  D3DKMT_HANDLE ObjectHandleArray[D3DDDI_MAX_OBJECT_WAITED_ON];
} D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT;
````


## -struct-fields

### -field hContext

[in] A handle to a context that waits for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies to occur.

### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 

### -field ObjectHandleArray

[in] An array of handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for. The <b>D3DDDI_MAX_OBJECT_WAITED_ON</b> constant, which is defined as 32, indicates the maximum number of synchronization events that the context can wait for.

## -remarks


## -requirements
<table>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
