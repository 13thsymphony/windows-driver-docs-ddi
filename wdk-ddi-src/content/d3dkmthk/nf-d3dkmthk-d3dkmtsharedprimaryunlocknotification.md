---
UID: NF:d3dkmthk.D3DKMTSharedPrimaryUnLockNotification
title: D3DKMTSharedPrimaryUnLockNotification function
author: windows-driver-content
description: The D3DKMTSharedPrimaryUnLockNotification function notifies the operating system that a shared primary surface was unlocked.
old-location: display\d3dkmtsharedprimaryunlocknotification.htm
old-project: display
ms.assetid: 1d602d09-cd80-4079-9132-1caced4d1eee
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmtsharedprimaryunlocknotification, d3dkmthk/D3DKMTSharedPrimaryUnLockNotification, D3DKMTSharedPrimaryUnLockNotification, D3DKMTSharedPrimaryUnLockNotification function [Display Devices], OpenGL_Functions_311a1879-e3f7-44e2-aa1a-0c070e45bf85.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTSharedPrimaryUnLockNotification
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTSharedPrimaryUnLockNotification function
The <b>D3DKMTSharedPrimaryUnLockNotification</b> function notifies the operating system that a shared primary surface was unlocked.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSharedPrimaryUnLockNotification(
  _In_ const D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION *pData
);
````

## Parameters

`D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION`

TBD


## Return Value

<b>D3DKMTSharedPrimaryUnLockNotification</b> returns one of the following values:

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
Notification about unlocking a shared primary surface was successfully performed.

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
 

This function might also return other NTSTATUS values.

## Remarks

The OpenGL ICD calls the <b>D3DKMTSharedPrimaryUnLockNotification</b> function to inform the operating system that an application just unlocked the GDI shared primary surface that exists on the graphics adapter and video present source that the <b>AdapterLuid</b> and <b>VidPnSourceId</b> members of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md">D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION</a> structure specify. The OpenGL ICD should call <b>D3DKMTSharedPrimaryUnLockNotification</b> after it calls the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtunlock.md">D3DKMTUnlock</a> function to unlock the GDI shared primary surface.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtunlock.md">D3DKMTUnlock</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md">D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSharedPrimaryUnLockNotification function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>