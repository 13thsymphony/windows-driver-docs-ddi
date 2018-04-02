---
UID: NC:d3dumddi.PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
author: windows-driver-content
description: The pfnCreateSynchronizationObjectCb function creates a synchronization object that a device context can signal and wait for.
old-location: display\pfncreatesynchronizationobjectcb.htm
old-project: display
ms.assetid: 1b87d3cc-685a-4768-b4fd-dbe0a0cbec37
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3Druntime_Functions_6c4f40ee-12b2-47a8-bbec-8591b730bef5.xml, PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB, d3dumddi/pfnCreateSynchronizationObjectCb, display.pfncreatesynchronizationobjectcb, pfnCreateSynchronizationObjectCb, pfnCreateSynchronizationObjectCb callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnCreateSynchronizationObjectCb
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB callback function
The <b>pfnCreateSynchronizationObjectCb</b> function creates a synchronization object that a device context can signal and wait for.

## Syntax

```
PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB Pfnd3dddiCreatesynchronizationobjectcb;

HRESULT Pfnd3dddiCreatesynchronizationobjectcb(
  HANDLE hDevice,
  D3DDDICB_CREATESYNCHRONIZATIONOBJECT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (that is, the graphics context) that will own the synchronization object that <b>pfnCreateSynchronizationObjectCb</b> creates.

`*`




## Return Value

<b>pfnCreateSynchronizationObjectCb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The synchronization object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnCreateSynchronizationObjectCb</b> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.

## Remarks

The <b>pfnCreateSynchronizationObjectCb</b> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544157">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/d33ca665-897d-4e99-b9a6-b794127fecfd">pfnWaitForSynchronizationObjectCb</a>


</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544157">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/d33ca665-897d-4e99-b9a6-b794127fecfd">pfnWaitForSynchronizationObjectCb</a>