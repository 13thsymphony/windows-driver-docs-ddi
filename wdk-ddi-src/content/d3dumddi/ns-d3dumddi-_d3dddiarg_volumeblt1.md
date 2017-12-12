---
UID: NS.D3DUMDDI._D3DDDIARG_VOLUMEBLT1
title: _D3DDDIARG_VOLUMEBLT1
author: windows-driver-content
description: Describes parameters for a volume bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_volumeblt1.htm
old-project: display
ms.assetid: 685aad54-03f5-4e3c-83a7-a44745acc4fb
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDIARG_VOLUMEBLT1, D3DDDIARG_VOLUMEBLT1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_VOLUMEBLT1
req.alt-loc: D3dumddi.h
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

# _D3DDDIARG_VOLUMEBLT1 structure



## -description
Describes parameters for a volume bit-block transfer (bitblt) operation.



## -syntax

````
typedef struct _D3DDDIARG_VOLUMEBLT1 {
  HANDLE    hDstResource;
  HANDLE    hSrcResource;
  UINT      DstX;
  UINT      DstY;
  UINT      DstZ;
  D3DDDIBOX SrcBox;
  UINT      CopyFlags;
} D3DDDIARG_VOLUMEBLT1;
````


## -struct-fields

### -field hDstResource

[in] A handle to the destination surface.


### -field hSrcResource

[in] A handle to the source surface.


### -field DstX

[in] The width, in screen coordinates, of the destination volume in which the source volume is copied.


### -field DstY

[in] The height, in screen coordinates, of the destination volume in which the source volume is copied.


### -field DstZ

[in] The depth, in screen coordinates, of the destination volume in which the source volume is copied.


### -field SrcBox

[in] A <a href="display.d3dddibox">D3DDDIBOX</a> structure that describes the source volume texture to copy to the destination.


### -field CopyFlags

A value that specifies characteristics of a copy operation as a bitwise OR of the values in the <a href="..\d3dumddi\ne-d3dumddi-d3dddi_copy_flags.md">D3DDDI_COPY_FLAGS</a> enumeration type.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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
<a href="..\d3dumddi\ne-d3dumddi-d3dddi_copy_flags.md">D3DDDI_COPY_FLAGS</a>
</dt>
<dt>
<a href="display.d3dddibox">D3DDDIBOX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_VOLUMEBLT1 structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

