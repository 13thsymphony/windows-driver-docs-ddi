---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvReadItemProperties
title: IWiaMiniDrv::drvReadItemProperties method
author: windows-driver-content
description: The IWiaMiniDrv::drvReadItemProperties method reads the driver item properties that need to be updated.
old-location: image\iwiaminidrv_drvreaditemproperties.htm
old-project: image
ms.assetid: 015c2e02-62aa-4037-9974-c8e4b8784fe5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv::drvReadItemProperties, drvReadItemProperties
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
req.alt-api: IWiaMiniDrv.drvReadItemProperties
req.alt-loc: wiamindr_lh.h
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
req.typenames: *PSCANWINDOW, SCANWINDOW
req.product: Windows 10 or later.
---

# IWiaMiniDrv::drvReadItemProperties method



## -description
The <b>IWiaMiniDrv::drvReadItemProperties</b> method reads the driver item properties that need to be updated.



## -syntax

````
HRESULT drvReadItemProperties(
  [in]        BYTE     *pWiasContext,
  [in]        LONG     lFlags,
  [in]        ULONG    nPropSpec,
  [in]  const PROPSPEC *pPropSpec,
  [out]       LONG     *plDevErrVal
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.


### -param lFlags [in]

Is reserved. Set to zero.


### -param nPropSpec [in]

Indicates the number of items in the <i>pPropSpec</i> array.


### -param pPropSpec [in]

Points to the first element of an array of PROPSPEC structures (defined in the Microsoft Windows SDK documentation). 


### -param plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


## -returns
On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.


## -remarks
In this method, the minidriver should read the requested properties from the device. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Me and in Windows XP and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamindr_lh.h (include Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/15068d10-5e24-427c-9684-24ce67b75ada">IWiaMiniDrv</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropbin.md">wiasWritePropBin</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropguid.md">wiasWritePropGuid</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritemultiple.md">wiasWriteMultiple</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545020">IWiaMiniDrv::drvWriteItemProperties</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvReadItemProperties method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

