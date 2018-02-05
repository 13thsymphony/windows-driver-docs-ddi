---
UID : NF:wiamindr_lh.IWiaMiniDrv.drvValidateItemProperties
title : IWiaMiniDrv::drvValidateItemProperties method
author : windows-driver-content
description : The IWiaMiniDrv::drvValidateItemProperties method validates an item's properties against the set of valid values for each property and will update those properties if necessary.
old-location : image\iwiaminidrv_drvvalidateitemproperties.htm
old-project : image
ms.assetid : 12052128-9ea7-41cd-bb75-be7175e26c12
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : IWiaMiniDrv, drvValidateItemProperties method [Imaging Devices], IWiaMiniDrv interface, drvValidateItemProperties method [Imaging Devices], image.iwiaminidrv_drvvalidateitemproperties, IWiaMiniDrv::drvValidateItemProperties, MiniDrv_b288e05c-a142-452a-9ac7-ffb2dfcae4cf.xml, drvValidateItemProperties, wiamindr_lh/IWiaMiniDrv::drvValidateItemProperties, IWiaMiniDrv interface [Imaging Devices], drvValidateItemProperties method
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


# drvValidateItemProperties method
The <b>IWiaMiniDrv::drvValidateItemProperties</b> method validates an item's properties against the set of valid values for each property and will update those properties if necessary.

## Syntax

````
HRESULT drvValidateItemProperties(
  [in]        BYTE     *pWiasContext,
  [in]        LONG     lFlags,
  [in]        ULONG    nPropSpec,
  [in]  const PROPSPEC *pPropSpec,
  [out]       LONG     *plDevErrVal
);
````

## Parameters

`__MIDL__IWiaMiniDrv0016`



`__MIDL__IWiaMiniDrv0017`



`__MIDL__IWiaMiniDrv0018`



`__MIDL__IWiaMiniDrv0019`



`__MIDL__IWiaMiniDrv0020`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>.

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later. Available in Windows Me and in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** | wiamindr_lh.h |

## See Also

<a href="..\wiamdef\nf-wiamdef-wiasvalidateitemproperties.md">wiasValidateItemProperties</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetitemtype.md">wiasGetItemType</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvValidateItemProperties method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>