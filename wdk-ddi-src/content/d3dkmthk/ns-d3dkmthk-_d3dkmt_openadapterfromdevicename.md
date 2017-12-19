---
UID: NS.D3DKMTHK._D3DKMT_OPENADAPTERFROMDEVICENAME
title: _D3DKMT_OPENADAPTERFROMDEVICENAME
author: windows-driver-content
description: The D3DKMT_OPENADAPTERFROMDEVICENAME structure describes the mapping of the given name of a device to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromdevicename.htm
old-project: display
ms.assetid: 4e633c7c-fd88-4b8f-9d29-2c7a3daa3d32
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_OPENADAPTERFROMDEVICENAME, D3DKMT_OPENADAPTERFROMDEVICENAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OPENADAPTERFROMDEVICENAME
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_OPENADAPTERFROMDEVICENAME structure



## -description
The D3DKMT_OPENADAPTERFROMDEVICENAME structure describes the mapping of the given name of a device to a graphics adapter handle and monitor output.



## -syntax

````
typedef struct _D3DKMT_OPENADAPTERFROMDEVICENAME {
  PCWSTR        pDeviceName;
  D3DKMT_HANDLE hAdapter;
  LUID          AdapterLuid;
} D3DKMT_OPENADAPTERFROMDEVICENAME;
````


## -struct-fields

### -field pDeviceName

[in] A Null-terminated string that contains the name of the device from which to open an adapter instance. 


### -field hAdapter

[out] A handle to the graphics adapter for the device that <b>pDeviceName</b> specifies. The adapter handle is returned from the call to the <a href="display.d3dkmtopenadapterfromdevicename">D3DKMTOpenAdapterFromDeviceName</a> function.


### -field AdapterLuid

[out] The locally unique identifier (<a href="kernel.luid">LUID</a>) of the graphics adapter for the device that <b>pDeviceName</b> specifies. The LUID is returned from the <a href="display.d3dkmtopenadapterfromdevicename">D3DKMTOpenAdapterFromDeviceName</a> call.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmtopenadapterfromdevicename">D3DKMTOpenAdapterFromDeviceName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENADAPTERFROMDEVICENAME structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

