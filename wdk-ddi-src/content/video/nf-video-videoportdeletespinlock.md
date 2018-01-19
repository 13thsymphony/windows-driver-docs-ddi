---
UID : NF:video.VideoPortDeleteSpinLock
title : VideoPortDeleteSpinLock function
author : windows-driver-content
description : The VideoPortDeleteSpinLock function deletes a given spin lock.
old-location : display\videoportdeletespinlock.htm
old-project : display
ms.assetid : 74845e4d-0fa1-4625-96a7-2fddec8b901d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortDeleteSpinLock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VideoPortDeleteSpinLock
req.alt-loc : Videoprt.sys
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Videoprt.lib
req.dll : Videoprt.sys
req.irql : <=DISPATCH_LEVEL
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
---


# VideoPortDeleteSpinLock function
The <b>VideoPortDeleteSpinLock</b> function deletes a given spin lock.

## Syntax

````
VP_STATUS VideoPortDeleteSpinLock(
  _In_ PVOID      HwDeviceExtension,
  _In_ PSPIN_LOCK SpinLock
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`SpinLock`

Pointer to the spin lock to delete.


## Return Value

If the spin lock is successfully deleted, <b>VideoPortDeleteSpinLock</b> returns NO_ERROR.

## Remarks

A miniport driver uses this function to delete a spin lock that was previously created in a call to <a href="..\video\nf-video-videoportcreatespinlock.md">VideoPortCreateSpinLock</a>.

This routine cannot be called from an ISR or from a <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a> callback requested where the <i>Priority</i> parameter is set to either <b>VpMediumPriority</b> or <b>VpHighPriority</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\video\nf-video-videoportcreatespinlock.md">VideoPortCreateSpinLock</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortDeleteSpinLock function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>