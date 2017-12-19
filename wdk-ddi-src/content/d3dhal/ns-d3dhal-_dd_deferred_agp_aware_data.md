---
UID: NS.D3DHAL._DD_DEFERRED_AGP_AWARE_DATA
title: _DD_DEFERRED_AGP_AWARE_DATA
author: windows-driver-content
description: DirectX 8.0 and later versions and NT-based operating systems only. DD_DEFERRED_AGP_AWARE_DATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for D3DGDI2_TYPE_DEFERRED_AGP_AWARE notifications.
old-location: display\dd_deferred_agp_aware_data.htm
old-project: display
ms.assetid: df36008a-2ee4-4e3e-8bad-7da1f27a695d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DD_DEFERRED_AGP_AWARE_DATA, DD_DEFERRED_AGP_AWARE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DD_DEFERRED_AGP_AWARE_DATA
req.alt-loc: d3dhal.h
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
---

# _DD_DEFERRED_AGP_AWARE_DATA structure



## -description

   DirectX 8.0 and later versions and NT-based operating systems only.
   

DD_DEFERRED_AGP_AWARE_DATA is the data structure pointed to by the <b>lpvData</b> field of <a href="display.dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for D3DGDI2_TYPE_DEFERRED_AGP_AWARE notifications.



## -syntax

````
typedef struct _DD_DEFERRED_AGP_AWARE_DATA {
  DD_GETDRIVERINFO2DATA gdi2;
} DD_DEFERRED_AGP_AWARE_DATA;
````


## -struct-fields

### -field gdi2

Specifies a <a href="display.dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


## -remarks
Whenever a display device is created, the driver receives a <b>GetDriverInfo2</b> call with D3DGDI2_TYPE_DEFERRED_AGP_AWARE type and can determine if it should disable its other mechanisms that handle AGP memory and instead use the D3DGDI2_TYPE_FREE_DEFERRED_AGP and D3DGDI2_TYPE_DEFER_AGP_FREES notifications that the runtime subsequently sends.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>
</dt>
<dt>
<a href="display.dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_DEFERRED_AGP_AWARE_DATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

