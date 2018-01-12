---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_GETMIPPACKING
title: PFND3DWDDM1_3DDI_GETMIPPACKING
author: windows-driver-content
description: For a given tiled resource, returns how many mips are packed, and how many tiles are needed to store all the packed mips.
old-location: display\getmippacking.htm
old-project: display
ms.assetid: 8AF361B5-279D-4525-AD98-843A4A746201
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetMipPacking
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3DWDDM1_3DDI_GETMIPPACKING callback



## -description
For a given tiled resource, returns how many mips are packed, and how many tiles are needed to store all the packed mips.



## -prototype

````
PFND3DWDDM1_3DDI_GETMIPPACKING GetMipPacking;

VOID APIENTRY* GetMipPacking(
        D3D10DDI_HDEVICE   hDevice,
        D3D10DDI_HRESOURCE hTiledResource,
  _Out_ UINT               *pNumPackedMips,
  _Out_ UINT               *pNumTilesForPackedMips
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device (graphics context).


### -param hTiledResource 

A handle to the tiled resource.


### -param pNumPackedMips [out]

A pointer to a variable that receives the number of mips that are packed, for a given array slice, including any mips that don't use the standard tile shapes.

If there is no packing, a value of zero should be returned.


### -param pNumTilesForPackedMips [out]

A pointer to a variable that receives the number of tiles that the packed mips fit into, for a given array slice.

This parameter is ignored if *<i>pNumPackedMips</i> returns zero.


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if an input parameter does not exist or is <b>NULL</b>.


## -remarks
Packed mips include cases where multiple small mips share tile(s) and also mips for which a given device cannot use standard tile shapes.  It's possible for an entire resource to be considered packed.

Applications are not told the tile shapes or layout for packed mips and must simply map 
all or none of the packed tiles if any of the mipmaps are to be accessed. 
Otherwise the observed mapping of individual pixels accessed are undefined  and are specific to the independent hardware vendor (IHV).

Mipmaps that have pixel dimensions that fully fill at least one standard-shaped tile in all 
dimensions are not allowed to be considered part of the set of packed mips. Otherwise
the runtime will remove the device on an invalid driver.  
One example of dimensions that a device can validly lump into 
the packed tiles (meaning the IHV can use his or her own custom tile breakdown) is
a mip that is at least one tile wide but less than a tile high.  Ideally though,
a device would use the standard tile breakdown for this case (so the application can
manage the tiles in a standard way).  If a device does need to use a custom tiling,
the application is not told what the tile breakdown is (only how many tiles are involved
in the packing overall), and thus loses some freedom.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
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
WDDM 1.3

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_GETMIPPACKING callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

