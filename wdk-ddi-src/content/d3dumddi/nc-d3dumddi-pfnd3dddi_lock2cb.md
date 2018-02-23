---
UID: NC:d3dumddi.PFND3DDDI_LOCK2CB
title: PFND3DDDI_LOCK2CB
author: windows-driver-content
description: The pfnLock2Cb function locks an allocation and obtains a pointer to the allocation from the display miniport driver or video memory manager.
old-location: display\pfnlock2cb.htm
old-project: display
ms.assetid: C046F34A-4304-4B96-8D7A-7A951016437F
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnlock2cb, pfnLock2Cb callback function [Display Devices], pfnLock2Cb, PFND3DDDI_LOCK2CB, PFND3DDDI_LOCK2CB, d3dumddi/pfnLock2Cb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnLock2Cb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_LOCK2CB callback function
The <b>pfnLock2Cb</b> function locks an allocation and obtains a pointer to the allocation from the display miniport driver or video memory manager.

## Syntax

```
PFND3DDDI_LOCK2CB Pfnd3dddiLock2cb;

HRESULT Pfnd3dddiLock2cb(
  HANDLE hDevice,
  D3DDDICB_LOCK2 *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

With the Windows Display Driver Model (WDDM) v2 it is now the user mode driver's responsibility to handle the following tasks:

<ul>
<li>Support no-overwrite and discard semantics. The video memory manager no longer supports renaming so it is up to the driver to implement renaming itself.</li>
<li>
Synchronization of other lock types (not no-overwrite or discard)

<ul>
<li>Must return <b>WasStillDrawing</b> if the user attempts to lock an allocation while specifying the <b>D3D1X_MAP_FLAG_DO_NOT_WAIT</b> flag.</li>
<li>The user mode driver must block if synchronization is required (ex. hardware is accessing the allocation). This must be implemented as a non-polling wait and make use of the new monitored fence synchronization objects.</li>
</ul>
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_lock2.md">D3DDDICB_LOCK2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_LOCK2CB callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>