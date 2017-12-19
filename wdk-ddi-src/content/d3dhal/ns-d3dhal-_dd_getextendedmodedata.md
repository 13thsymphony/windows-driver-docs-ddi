---
UID: NS.D3DHAL._DD_GETEXTENDEDMODEDATA
title: _DD_GETEXTENDEDMODEDATA
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_GETEXTENDEDMODEDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODE.
old-location: display\dd_getextendedmodedata.htm
old-project: display
ms.assetid: 50b2a1fd-4214-4ad8-b087-f48c14dbe587
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DD_GETEXTENDEDMODEDATA, DD_GETEXTENDEDMODEDATA
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
req.alt-api: DD_GETEXTENDEDMODEDATA
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

# _DD_GETEXTENDEDMODEDATA structure



## -description

   DirectX 9.0 and later versions only.
   

DD_GETEXTENDEDMODEDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="display.dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETEXTENDEDMODE.



## -syntax

````
typedef struct _DD_GETEXTENDEDMODEDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwModeIndex;
  D3DDISPLAYMODE        mode;
} DD_GETEXTENDEDMODEDATA;
````


## -struct-fields

### -field gdi2

Specifies a <a href="display.dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwModeIndex

Specifies the index of the display mode to return.


### -field mode

Receives a D3DDISPLAYMODE structure that specifies the actual display mode.


## -remarks
The runtime identifies the display mode to be returned with an integer index whose value varies between zero and one less than the number of supported display modes that were reported earlier by the driver in a DD_GETDRIVERINFO2DATA query with the type D3DGDI2_TYPE_GETEXTENDEDMODECOUNT. How these indices are mapped to actual display modes is left to the driver. However, each index must map uniquely to one supported display mode. The order in which the display modes are reported is not significant. 

When processing this <b>GetDriverInfo2</b> request the driver should read the value in the <b>dwModeIndex</b> member and map that value to one of the supported display modes (probably by using the value in <b>dwModeIndex</b> as an index into an array of D3DDISPLAYMODE structures). The driver should then copy that display mode into the <b>mode</b> member. The runtime guarantees that it only passes an index to the driver that is in the range zero to one less than the number of display modes reported by the driver. The range of the index should be validated in the debug driver build.

For more information about D3DDISPLAYMODE, see the DirectX SDK documentation.


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
<dt>
<a href="display.dd_getextendedmodecountdata">DD_GETEXTENDEDMODECOUNTDATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETEXTENDEDMODEDATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

