---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvReadItemProperties
title: IWiaMiniDrv::drvReadItemProperties method
author: windows-driver-content
description: The IWiaMiniDrv::drvReadItemProperties method reads the driver item properties that need to be updated.
old-location: image\iwiaminidrv_drvreaditemproperties.htm
old-project: image
ms.assetid: 015c2e02-62aa-4037-9974-c8e4b8784fe5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], drvReadItemProperties method, IWiaMiniDrv::drvReadItemProperties, MiniDrv_515d9cc7-c76a-4a15-9cc1-59be834382fe.xml, drvReadItemProperties method [Imaging Devices], drvReadItemProperties method [Imaging Devices], IWiaMiniDrv interface, drvReadItemProperties,IWiaMiniDrv.drvReadItemProperties, image.iwiaminidrv_drvreaditemproperties, wiamindr_lh/IWiaMiniDrv::drvReadItemProperties
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
-	IWiaMiniDrv.drvReadItemProperties
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# drvReadItemProperties method
The <b>IWiaMiniDrv::drvReadItemProperties</b> method reads the driver item properties that need to be updated.

## Syntax

````
HRESULT drvReadItemProperties(
  [in]        BYTE     *pWiasContext,
  [in]        LONG     lFlags,
  [in]        ULONG    nPropSpec,
  [in]  const PROPSPEC *pPropSpec,
  [out]       LONG     *plDevErrVal
);
````

## Parameters

`__MIDL__IWiaMiniDrv0025`



`__MIDL__IWiaMiniDrv0026`



`__MIDL__IWiaMiniDrv0027`



`__MIDL__IWiaMiniDrv0028`



`__MIDL__IWiaMiniDrv0029`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.

## Remarks

In this method, the minidriver should read the requested properties from the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritemultiple.md">wiasWriteMultiple</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropguid.md">wiasWritePropGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545020">IWiaMiniDrv::drvWriteItemProperties</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropbin.md">wiasWritePropBin</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvReadItemProperties method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>