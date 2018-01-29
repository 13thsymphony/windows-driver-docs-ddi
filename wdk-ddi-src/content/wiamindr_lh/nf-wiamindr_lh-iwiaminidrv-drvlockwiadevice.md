---
UID : NF:wiamindr_lh.IWiaMiniDrv.drvLockWiaDevice
title : IWiaMiniDrv::drvLockWiaDevice method
author : windows-driver-content
description : The IWiaMiniDrv::drvLockWiaDevice method locks the WIA hardware device so that only the current minidriver can access it.
old-location : image\iwiaminidrv_drvlockwiadevice.htm
old-project : image
ms.assetid : 674e0a65-1763-41b0-896b-2ef9debc32a5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : drvLockWiaDevice, drvLockWiaDevice method [Imaging Devices], MiniDrv_5ae2a5c5-524c-46ce-8ae4-d8edd5d76fcc.xml, image.iwiaminidrv_drvlockwiadevice, drvLockWiaDevice method [Imaging Devices], IWiaMiniDrv interface, wiamindr_lh/IWiaMiniDrv::drvLockWiaDevice, IWiaMiniDrv interface [Imaging Devices], drvLockWiaDevice method, IWiaMiniDrv::drvLockWiaDevice, IWiaMiniDrv
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wiamindr_lh.h
req.include-header : Wiamindr.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Me and in Windows XP and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wiamindr_lh.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SCANWINDOW, *PSCANWINDOW
req.product : Windows 10 or later.
---


# drvLockWiaDevice method
The <b>IWiaMiniDrv::drvLockWiaDevice</b> method locks the WIA hardware device so that only the current minidriver can access it.

## Syntax

````
HRESULT drvLockWiaDevice(
  [in]  BYTE *pWiasContext,
  [in]  LONG lFlags,
  [out] LONG *plDevErrVal
);
````

## Parameters

`__MIDL__IWiaMiniDrv0030`



`__MIDL__IWiaMiniDrv0031`



`__MIDL__IWiaMiniDrv0032`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>.

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.

## Remarks

The <b>IWiaMiniDrv::drvLockWiaDevice</b> method is used to lock access to the device. This is typically done before properties are written to the device or before a data transfer. The <b>IWiaMiniDrv::drvLockWiaDevice </b>method should be implemented using the <b>IStiDevice</b> interface's lock device method, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545012">IWiaMiniDrv::drvUnLockWiaDevice</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvLockWiaDevice method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>