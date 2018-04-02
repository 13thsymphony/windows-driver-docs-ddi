---
UID: NF:d3dkmthk.D3DKMTSharedPrimaryLockNotification
title: D3DKMTSharedPrimaryLockNotification function
author: windows-driver-content
description: The D3DKMTSharedPrimaryLockNotification function notifies the operating system about an upcoming lock to a shared primary surface.
old-location: display\d3dkmtsharedprimarylocknotification.htm
old-project: display
ms.assetid: 4104b137-dd32-4566-a46a-f20ef6b602c6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTSharedPrimaryLockNotification, D3DKMTSharedPrimaryLockNotification function [Display Devices], OpenGL_Functions_a6696797-0a53-4687-8a70-4878b550fa03.xml, d3dkmthk/D3DKMTSharedPrimaryLockNotification, display.d3dkmtsharedprimarylocknotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSharedPrimaryLockNotification
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTSharedPrimaryLockNotification function
The <b>D3DKMTSharedPrimaryLockNotification</b> function notifies the operating system about an upcoming lock to a shared primary surface.

## Syntax

```
NTSTATUS D3DKMTSharedPrimaryLockNotification(
  CONST *D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
);
```

## Parameters

`D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION`

TBD


## Return Value

<b>D3DKMTSharedPrimaryLockNotification</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Notification about an upcoming lock to a shared primary surface was successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547208">D3DKMTSharedPrimaryLockNotification</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values that are defined in Ntstatus.h.

## Remarks

The OpenGL ICD calls the <b>D3DKMTSharedPrimaryLockNotification</b> function to inform the operating system that an application is about to lock the GDI shared primary surface that exists on the graphics adapter and video present source that the <b>AdapterLuid</b> and <b>VidPnSourceId</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548329">D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION</a> structure specify. The OpenGL ICD must call <b>D3DKMTSharedPrimaryLockNotification</b> before it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547028">D3DKMTLock</a> function for the GDI shared primary surface to ensure that the operating system disables all sprites that intersect with the lock region that the <b>LockRect</b> member of D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION specifies.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547028">D3DKMTLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548329">D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION</a>