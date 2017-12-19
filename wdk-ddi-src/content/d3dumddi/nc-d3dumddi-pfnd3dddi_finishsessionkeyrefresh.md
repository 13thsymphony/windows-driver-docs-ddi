---
UID: NC.d3dumddi.PFND3DDDI_FINISHSESSIONKEYREFRESH
title: PFND3DDDI_FINISHSESSIONKEYREFRESH
author: windows-driver-content
description: The FinishSessionKeyRefresh function indicates that all buffers from that point in time use the updated session key value.
old-location: display\finishsessionkeyrefresh.htm
old-project: display
ms.assetid: e245f6f9-f4ea-429d-8421-be4fef1bf17e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: The FinishSessionKeyRefresh function is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FinishSessionKeyRefresh
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_FINISHSESSIONKEYREFRESH callback



## -description
The <i>FinishSessionKeyRefresh</i> function indicates that all buffers from that point in time use the updated session key value. 



## -prototype

````
PFND3DDDI_FINISHSESSIONKEYREFRESH FinishSessionKeyRefresh;

__checkReturn HRESULT APIENTRY FinishSessionKeyRefresh(
  _In_       HANDLE                            hDevice,
  _In_ const D3DDDIARG_FINISHSESSIONKEYREFRESH *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="display.d3dddiarg_finishsessionkeyrefresh">D3DDDIARG_FINISHSESSIONKEYREFRESH</a> structure that describes the session. 


## -returns
<i>FinishSessionKeyRefresh</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The session is successfully updated. 
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>The driver does not support the <i>FinishSessionKeyRefresh</i> function. 

 


## -remarks
The hardware and driver can optionally support the <i>FinishSessionKeyRefresh</i> function for all crypto types.

When the Direct3D runtime calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="display.d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to. 

When the runtime subsequently calls the driver's <i>FinishSessionKeyRefresh</i> function, the driver performs an XOR operation of the random number with the session key.


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
The <i>FinishSessionKeyRefresh</i> function is supported beginning with the Windows 7 operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_finishsessionkeyrefresh">D3DDDIARG_FINISHSESSIONKEYREFRESH</a>
</dt>
<dt>
<a href="display.d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FINISHSESSIONKEYREFRESH callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

