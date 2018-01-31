---
UID : NF:wiamindr_lh.IWiaMiniDrv.drvWriteItemProperties
title : IWiaMiniDrv::drvWriteItemProperties method
author : windows-driver-content
description : The IWiaMiniDrv::drvWriteItemProperties method writes driver item properties to a WIA hardware device.
old-location : image\iwiaminidrv_drvwriteitemproperties.htm
old-project : image
ms.assetid : 350cb7f6-499f-4fbc-b5c0-6f4daf2a2af0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : MiniDrv_9296f23a-679c-48e0-b594-ece8a1030e50.xml, IWiaMiniDrv::drvWriteItemProperties, IWiaMiniDrv, drvWriteItemProperties method [Imaging Devices], IWiaMiniDrv interface, image.iwiaminidrv_drvwriteitemproperties, IWiaMiniDrv interface [Imaging Devices], drvWriteItemProperties method, drvWriteItemProperties, drvWriteItemProperties method [Imaging Devices], wiamindr_lh/IWiaMiniDrv::drvWriteItemProperties
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
req.typenames : "*PSCANWINDOW, SCANWINDOW"
req.product : Windows 10 or later.
---


# drvWriteItemProperties method
The <b>IWiaMiniDrv::drvWriteItemProperties</b> method writes driver item properties to a WIA hardware device.

## Syntax

````
HRESULT drvWriteItemProperties(
  [in]  BYTE                      *pWiasContext,
  [in]  LONG                      lFlags,
  [in]  PMINIDRV_TRANSFER_CONTEXT pmdtc,
  [out] LONG                      *plDevErrVal
);
````

## Parameters

`__MIDL__IWiaMiniDrv0021`



`__MIDL__IWiaMiniDrv0022`



`__MIDL__IWiaMiniDrv0023`



`__MIDL__IWiaMiniDrv0024`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>.

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.


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

<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetrootitem.md">wiasGetRootItem</a>

<a href="..\wiamdef\nf-wiamdef-wiasreadproplong.md">wiasReadPropLong</a>

<a href="..\wiamdef\nf-wiamdef-wiasreadpropfloat.md">wiasReadPropFloat</a>

<a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a>

<a href="..\wiamdef\nf-wiamdef-wiasreadpropguid.md">wiasReadPropGuid</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>

<a href="..\wiamdef\nf-wiamdef-wiasreadmultiple.md">wiasReadMultiple</a>

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>

<a href="..\wiamdef\nf-wiamdef-wiasreadpropstr.md">wiasReadPropStr</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvWriteItemProperties method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>