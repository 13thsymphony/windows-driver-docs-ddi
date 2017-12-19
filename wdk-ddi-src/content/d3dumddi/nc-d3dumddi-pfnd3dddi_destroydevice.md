---
UID: NC.d3dumddi.PFND3DDDI_DESTROYDEVICE
title: PFND3DDDI_DESTROYDEVICE
author: windows-driver-content
description: The DestroyDevice function destroys a graphics context.
old-location: display\destroydevice.htm
old-project: display
ms.assetid: a3c158c2-6c0d-4da0-80f4-569971b10673
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
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
req.alt-api: DestroyDevice
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

# PFND3DDDI_DESTROYDEVICE callback



## -description
The <i>DestroyDevice</i> function destroys a graphics context.



## -prototype

````
PFND3DDDI_DESTROYDEVICE DestroyDevice;

__checkReturn HRESULT APIENTRY DestroyDevice(
  _In_ HANDLE hDevice
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context) being destroyed.


## -returns
<i>DestroyDevice</i> returns S_OK or an appropriate error result. 


## -remarks
The driver should free all of the resources that it allocated for the device and clean up any internal tracking data structures. 

Before the driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> function to release allocations, the driver must ensure that the allocations are unlocked. In other words, in the lifetime of a device, every call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function to lock an allocation must be paired with a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function to unlock the allocation. However, in one call to <i>pfnUnlockCb</i>, the driver can unlock multiple allocations that were each allocated in separate <i>pfnLockCb</i> calls.


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYDEVICE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

