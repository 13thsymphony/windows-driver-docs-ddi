---
UID: NF.wiamindr_lh.IWiaMiniDrv.drvFreeDrvItemContext
title: IWiaMiniDrv::drvFreeDrvItemContext
author: windows-driver-content
description: The IWiaMiniDrv::drvFreeDrvItemContext method frees a device-specific context.
old-location: image\iwiaminidrv_drvfreedrvitemcontext.htm
old-project: image
ms.assetid: bc4f751f-d92a-47e6-8cbe-0a587292b160
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: IWiaMiniDrv, drvFreeDrvItemContext, IWiaMiniDrv::drvFreeDrvItemContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaMiniDrv.drvFreeDrvItemContext
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
req.iface: IWiaMiniDrv
req.product: Windows 10 or later.
---

# IWiaMiniDrv::drvFreeDrvItemContext method



## -description
<p>The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.</p>


## -syntax

````
HRESULT drvFreeDrvItemContext(
  [in]  LONG lFlags,
  [in]  BYTE *pSpecContext,
  [out] LONG *plDevErrVal
);
````


## -parameters
<dl>

### -param <i>lFlags</i> [in]

<dd>
<p>Is currently unused.</p>
</dd>

### -param <i>pSpecContext</i> [in]

<dd>
<p>Points to a device-specific context. </p>
</dd>

### -param <i>plDevErrVal</i> [out]

<dd>
<p>Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.</p>
</dd>
</dl>

## -returns
<p>On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code in the memory pointed to by <i>plDevErrVal</i>. </p>

<p>The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.

</p>

## -remarks
<p>When a driver item is deleted, the WIA service frees the driver item context. This method informs the minidriver that the context is ready to be freed. The minidriver should free any memory that it allocated for the context. For example, in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>, a camera minidriver might allocate a cache to store the thumbnail for an item, and store a pointer to this cache in the driver item context. The minidriver would then free the cache in this method.</p>

<p>When a driver item is deleted, the WIA service frees the driver item context. This method informs the minidriver that the context is ready to be freed. The minidriver should free any memory that it allocated for the context. For example, in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>, a camera minidriver might allocate a cache to store the thumbnail for an item, and store a pointer to this cache in the driver item context. The minidriver would then free the cache in this method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Me and in Windows XP and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvFreeDrvItemContext method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
