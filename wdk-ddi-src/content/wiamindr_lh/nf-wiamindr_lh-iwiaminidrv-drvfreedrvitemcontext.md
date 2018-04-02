---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvFreeDrvItemContext
title: IWiaMiniDrv::drvFreeDrvItemContext method
author: windows-driver-content
description: The IWiaMiniDrv::drvFreeDrvItemContext method frees a device-specific context.
old-location: image\iwiaminidrv_drvfreedrvitemcontext.htm
old-project: image
ms.assetid: bc4f751f-d92a-47e6-8cbe-0a587292b160
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], drvFreeDrvItemContext method, IWiaMiniDrv::drvFreeDrvItemContext, MiniDrv_59a7d220-cd1d-4cc2-870a-3260feaba7e9.xml, drvFreeDrvItemContext method [Imaging Devices], drvFreeDrvItemContext method [Imaging Devices], IWiaMiniDrv interface, drvFreeDrvItemContext,IWiaMiniDrv.drvFreeDrvItemContext, image.iwiaminidrv_drvfreedrvitemcontext, wiamindr_lh/IWiaMiniDrv::drvFreeDrvItemContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
-	COM
api_location:
-	wiamindr_lh.h
api_name:
-	IWiaMiniDrv.drvFreeDrvItemContext
product:
- Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# IWiaMiniDrv::drvFreeDrvItemContext method
The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.

## Syntax

```
HRESULT drvFreeDrvItemContext(
  LONG __MIDL__IWiaMiniDrv0056,
  BYTE *__MIDL__IWiaMiniDrv0057,
  LONG *__MIDL__IWiaMiniDrv0058
);
```

## Parameters

`__MIDL__IWiaMiniDrv0056`



`__MIDL__IWiaMiniDrv0057`



`__MIDL__IWiaMiniDrv0058`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.

## Remarks

When a driver item is deleted, the WIA service frees the driver item context. This method informs the minidriver that the context is ready to be freed. The minidriver should free any memory that it allocated for the context. For example, in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>, a camera minidriver might allocate a cache to store the thumbnail for an item, and store a pointer to this cache in the driver item context. The minidriver would then free the cache in this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="https://msdn.microsoft.com/15068d10-5e24-427c-9684-24ce67b75ada">IWiaMiniDrv</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>