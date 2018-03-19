---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvUnLockWiaDevice
title: IWiaMiniDrv::drvUnLockWiaDevice method
author: windows-driver-content
description: The IWiaMiniDrv::drvUnLockWiaDevice method unlocks the WIA hardware device so that any minidriver can access it.
old-location: image\iwiaminidrv_drvunlockwiadevice.htm
old-project: image
ms.assetid: 134d224a-d472-4d74-be3e-069dbb46a65c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], drvUnLockWiaDevice method, IWiaMiniDrv::drvUnLockWiaDevice, MiniDrv_596d3499-1e4a-4147-838f-db4f56f30716.xml, drvUnLockWiaDevice method [Imaging Devices], drvUnLockWiaDevice method [Imaging Devices], IWiaMiniDrv interface, drvUnLockWiaDevice,IWiaMiniDrv.drvUnLockWiaDevice, image.iwiaminidrv_drvunlockwiadevice, wiamindr_lh/IWiaMiniDrv::drvUnLockWiaDevice
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
-	IWiaMiniDrv.drvUnLockWiaDevice
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# drvUnLockWiaDevice method
The <b>IWiaMiniDrv::drvUnLockWiaDevice</b> method unlocks the WIA hardware device so that any minidriver can access it.

## Syntax

````
HRESULT drvUnLockWiaDevice(
  [in]  BYTE *pWiasContext,
  [in]  LONG lFlags,
  [out] LONG *plDevErrVal
);
````

## Parameters

`__MIDL__IWiaMiniDrv0033`



`__MIDL__IWiaMiniDrv0034`



`__MIDL__IWiaMiniDrv0035`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>.

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.

## Remarks

The method <b>IWiaMiniDrv::drvUnLockWiaDevice</b> is used to allow access to the device after the lock is no longer needed. It is typically called by the WIA service after properties are written to the device or after a data transfer. 

The minidriver's implementation of the <b>IWiaMiniDrv::drvUnLockWiaDevice</b> method should use the STI unlock device method <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544995">IWiaMiniDrv::drvLockWiaDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>