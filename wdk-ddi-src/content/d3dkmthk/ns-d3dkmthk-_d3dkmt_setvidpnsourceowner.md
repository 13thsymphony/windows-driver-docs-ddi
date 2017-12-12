---
UID: NS.D3DKMTHK._D3DKMT_SETVIDPNSOURCEOWNER
title: _D3DKMT_SETVIDPNSOURCEOWNER
author: windows-driver-content
description: The D3DKMT_SETVIDPNSOURCEOWNER structure describes the parameters for setting or releasing the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location: display\d3dkmt_setvidpnsourceowner.htm
old-project: display
ms.assetid: 9154848b-ecbe-4f21-9d27-9013f97c5dde
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_SETVIDPNSOURCEOWNER, D3DKMT_SETVIDPNSOURCEOWNER
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
req.alt-api: D3DKMT_SETVIDPNSOURCEOWNER
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

# _D3DKMT_SETVIDPNSOURCEOWNER structure



## -description
The D3DKMT_SETVIDPNSOURCEOWNER structure describes the parameters for setting or releasing the video present source in the path of a video present network (VidPN) topology that owns the VidPN.



## -syntax

````
typedef struct _D3DKMT_SETVIDPNSOURCEOWNER {
  D3DKMT_HANDLE                        hDevice;
  const D3DKMT_VIDPNSOURCEOWNER_TYPE   *pType;
  const D3DDDI_VIDEO_PRESENT_SOURCE_ID *pVidPnSourceId;
  UINT                                 VidPnSourceCount;
} D3DKMT_SETVIDPNSOURCEOWNER;
````


## -struct-fields

### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that acquires or releases the VidPN source owner.


### -field pType

[in] An array of owner types. Elements of the array can contain the following values from the D3DKMT_VIDPNSOURCEOWNER_TYPE enumeration type.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DKMT_VIDPNSOURCEOWNER_UNOWNED (0)

</td>
<td>
No owner, or GDI is the owner.

</td>
</tr>
<tr>
<td>
D3DKMT_VIDPNSOURCEOWNER_SHARED (1)

</td>
<td>
A shared owner. That is, the owner can yield to any exclusive owner. This type is not available to legacy devices.

</td>
</tr>
<tr>
<td>
D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVE (2)

</td>
<td>
An exclusive owner without shared GDI primary.

</td>
</tr>
<tr>
<td>
D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVEGDI (3)

</td>
<td>
An exclusive owner with shared GDI primary. This owner must exclusively own all of the VidPn sources. This type is available only to legacy devices.

</td>
</tr>
</table>
 


### -field pVidPnSourceId

[in] An array of zero-based identification numbers of the video present sources in paths of a video present network (VidPN) topology.


### -field VidPnSourceCount

The number of valid entries in the array that <b>pVidPnSourceId</b> specifies.


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
<a href="display.d3dkmtsetvidpnsourceowner">D3DKMTSetVidPnSourceOwner</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETVIDPNSOURCEOWNER structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

