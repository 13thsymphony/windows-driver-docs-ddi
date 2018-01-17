---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEISSTAGINGBUSY
title: PFND3D10DDI_RESOURCEISSTAGINGBUSY
author: windows-driver-content
description: The ResourceIsStagingBusy function determines whether a resource is currently being used by the graphics pipeline.
old-location: display\resourceisstagingbusy.htm
old-project: display
ms.assetid: df8498e2-a3b5-4bc8-b6d2-0d444f1d1485
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _POWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ResourceIsStagingBusy
req.alt-loc: d3d10umddi.h
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
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---

# PFND3D10DDI_RESOURCEISSTAGINGBUSY callback



## -description
The <i>ResourceIsStagingBusy</i> function determines whether a resource is currently being used by the graphics pipeline. 



## -prototype

````
PFND3D10DDI_RESOURCEISSTAGINGBUSY ResourceIsStagingBusy;

BOOL APIENTRY ResourceIsStagingBusy(
  _In_ D3D10DDI_HDEVICE   hDevice,
  _In_ D3D10DDI_HRESOURCE hResource
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hResource [in]

 A handle to the resource.


## -returns
<i>ResourceIsStagingBusy</i> returns a Boolean value that specifies whether the resource that the <i>hResource</i> parameter specifies is currently being used by the graphics pipeline. <b>TRUE</b> indicates that the graphics pipeline currently uses the resource; <b>FALSE</b> indicates that the graphics pipeline currently does not use the resource. 


## -remarks
The Microsoft Direct3D runtime call to <i>ResourceIsStagingBusy</i> is roughly equivalent to the call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function with the D3D10_DDI_MAP_FLAG_DONOTWAIT flag set in the <i>Flags</i> parameter, except that <i>ResourceMap</i> can perform only one subresource at a time and <i>ResourceIsStagingBusy</i> can be called while some of the subresources are currently mapped. 

The user-mode display driver is not required to flush any partially built command buffer. If the driver is resident in the partially built command buffer, the driver qualifies as busy. 

<i>ResourceIsStagingBusy</i> should not encounter any errors. However, <i>ResourceIsStagingBusy</i> might call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function for critical errors. 


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RESOURCEISSTAGINGBUSY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

