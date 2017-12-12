---
UID: NS.D3DKMTHK._D3DKMT_DESTROYOVERLAY
title: _D3DKMT_DESTROYOVERLAY
author: windows-driver-content
description: The D3DKMT_DESTROYOVERLAY structure contains the handle to the overlay to destroy.
old-location: display\d3dkmt_destroyoverlay.htm
old-project: display
ms.assetid: b1b8554f-8d6b-4c2e-b6b8-fcbfc97f5dd9
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_DESTROYOVERLAY, D3DKMT_DESTROYOVERLAY
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
req.alt-api: D3DKMT_DESTROYOVERLAY
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

# _D3DKMT_DESTROYOVERLAY structure



## -description
The D3DKMT_DESTROYOVERLAY structure contains the handle to the overlay to destroy.



## -syntax

````
typedef struct _D3DKMT_DESTROYOVERLAY {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hOverlay;
} D3DKMT_DESTROYOVERLAY;
````


## -struct-fields

### -field hDevice

[in] A handle to the device that the overlay is associated with.


### -field hOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to destroy. 


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
<a href="display.d3dkmtdestroyoverlay">D3DKMTDestroyOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DESTROYOVERLAY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

