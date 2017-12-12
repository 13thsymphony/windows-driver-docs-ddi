---
UID: NC.d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Inserts a wait command for the specified synchronization objects in the specified context command stream. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\pfnwaitforsynchronizationobject2cb.htm
old-project: display
ms.assetid: 4542C49F-C26C-45BE-B961-C5F65BDA78CF
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnWaitForSynchronizationObject2Cb
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

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback



## -description
Inserts a wait command for the specified synchronization objects in the specified context command stream. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.



## -prototype

````
PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB pfnWaitForSynchronizationObject2Cb;

__checkReturn HRESULT APIENTRY CALLBACK* pfnWaitForSynchronizationObject2Cb(
  _In_       HANDLE                                 hDevice,
  _In_ const D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param pData [in]

A pointer to a <a href="display.d3dddicb_waitforsynchronizationobject2">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context DMA stream that are required to set up the wait.


## -returns

      Returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The wait was successfully set up.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.


## -remarks
The <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="display.d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:


<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>


<i>pfnWaitForSynchronizationObject2Cb</i>

Do not call this function if the synchronization object is of type <b>D3DDDI_CPU_NOTIFICATION</b>—namely, the <b>Type</b> member of the <a href="display.d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_CPU_NOTIFICATION</b>.<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>



## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
<a href="display.d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="display.d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>
</dt>
<dt>
<a href="display.d3dddicb_createsynchronizationobject2">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

