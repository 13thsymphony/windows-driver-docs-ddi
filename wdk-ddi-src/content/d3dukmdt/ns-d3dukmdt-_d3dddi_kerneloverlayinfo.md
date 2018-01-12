---
UID: NS:d3dukmdt._D3DDDI_KERNELOVERLAYINFO
title: _D3DDDI_KERNELOVERLAYINFO
author: windows-driver-content
description: The D3DDDI_KERNELOVERLAYINFO structure describes information for a kernel-mode overlay object.
old-location: display\d3dddi_kerneloverlayinfo.htm
old-project: display
ms.assetid: 0a9685f8-f201-4d1b-aef6-c4ac78100a80
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDI_KERNELOVERLAYINFO, D3DDDI_KERNELOVERLAYINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_KERNELOVERLAYINFO
req.alt-loc: d3dukmdt.h
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
req.typenames: D3DDDI_KERNELOVERLAYINFO
---

# _D3DDDI_KERNELOVERLAYINFO structure



## -description
The D3DDDI_KERNELOVERLAYINFO structure describes information for a kernel-mode overlay object.



## -syntax

````
typedef struct _D3DDDI_KERNELOVERLAYINFO {
  D3DKMT_HANDLE hAllocation;
  D3DDDIRECT    DstRect;
  D3DDDIRECT    SrcRect;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3DDDI_KERNELOVERLAYINFO;
````


## -struct-fields

### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation to be displayed.


### -field DstRect

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddirect.md">D3DDDIRECT</a> structure that contains the overlay destination rectangle in device coordinates.


### -field SrcRect

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddirect.md">D3DDDIRECT</a> structure that contains the overlay source rectangle in device coordinates.


### -field pPrivateDriverData

[in] A pointer to a block of private data, which is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that is pointed to by <b>pPrivateDriverData</b>.


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
<dt>D3dukmdt.h (include D3dukmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddirect.md">D3DDDIRECT</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_KERNELOVERLAYINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

