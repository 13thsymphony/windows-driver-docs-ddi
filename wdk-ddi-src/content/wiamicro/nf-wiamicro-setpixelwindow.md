---
UID: NF.wiamicro.SetPixelWindow
title: SetPixelWindow function
author: windows-driver-content
description: The SetPixelWindow function sets the image area to be scanned.
old-location: image\setpixelwindow.htm
old-project: Image
ms.assetid: e1b5af5d-9bb8-4bf0-898a-5972f1f09a35
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SetPixelWindow
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetPixelWindow
req.alt-loc: wiamicro.h
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
req.product: Windows 10 or later.
---

# SetPixelWindow function



## -description
The <b>SetPixelWindow </b>function sets the image area to be scanned.



## -syntax

````
WIAMICRO_API HRESULT SetPixelWindow(
  _Inout_ PSCANINFO pScanInfo,
          LONG      x,
          LONG      y,
          LONG      xExtent,
          LONG      yExtent
);
````


## -parameters

### -param pScanInfo [in, out]

Points to a <a href="image.scaninfo">SCANINFO</a> structure that represents the current state of the device. This is stored by the WIA Flatbed driver to guarantee synchronized settings between the microdriver and the WIA Flatbed driver.


### -param x 

Specifies the horizontal position value for the left side of the selection rectangle in pixels. 


### -param y 

Specifies the vertical position value for the top of the selection rectangle in pixels.


### -param xExtent 

Specifies the width of the selection rectangle in pixels. 


### -param yExtent 

Specifies the height of the selection rectangle in pixels. 


## -returns
If the function succeeds, it returns S_OK. If the function fails, it returns a standard COM error code.


## -remarks
In this function, the microdriver should set up the <b>Window</b> member of the <a href="image.scaninfo">SCANINFO</a> structure, making any device-specific adjustments that are necessary. 


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
Available in Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamicro.h (include Wiamicro.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.scaninfo">SCANINFO</a>
</dt>
<dt>
<a href="image.wia_microdriver_structures">WIA Microdriver Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20SetPixelWindow function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

