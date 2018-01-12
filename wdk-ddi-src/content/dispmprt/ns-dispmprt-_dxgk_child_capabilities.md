---
UID: NS:dispmprt._DXGK_CHILD_CAPABILITIES
title: _DXGK_CHILD_CAPABILITIES
author: windows-driver-content
description: The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter.
old-location: display\dxgk_child_capabilities.htm
old-project: display
ms.assetid: 6ab6a505-ad02-4dce-8061-bba13081208a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_CHILD_CAPABILITIES, DXGK_CHILD_CAPABILITIES, *PDXGK_CHILD_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_CHILD_CAPABILITIES
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGK_CHILD_CAPABILITIES, *PDXGK_CHILD_CAPABILITIES
---

# _DXGK_CHILD_CAPABILITIES structure



## -description
The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter.



## -syntax

````
typedef struct _DXGK_CHILD_CAPABILITIES {
  union {
    DXGK_VIDEO_OUTPUT_CAPABILITIES VideoOutput;
    struct {
      UINT MustBeZero;
    } Other;
    DXGK_INTEGRATED_DISPLAY_CHILD  IntegratedDisplayChild;
  } Type;
  DXGK_CHILD_DEVICE_HPD_AWARENESS HpdAwareness;
} DXGK_CHILD_CAPABILITIES, *PDXGK_CHILD_CAPABILITIES;
````


## -struct-fields

### -field Type


      A union that can contain either video output information or other information in the following members. 
     


### -field VideoOutput

A <a href="..\dispmprt\ns-dispmprt-_dxgk_video_output_capabilities.md">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure that contains information about a video output. This member is meaningful only if the child device has type <b>TypeVideoOutput</b>.


### -field Other

A structure whose only member must be equal to zero if the child device has type <b>TypeOther</b>.


### -field MustBeZero

A UINT value that must be equal to zero.

</dd>
</dl>

### -field IntegratedDisplayChild

Returns the integrated display child specific fields of the child capabilities.

</dd>
</dl>

### -field HpdAwareness

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgk_child_device_hpd_awareness.md">DXGK_CHILD_DEVICE_HPD_AWARENESS</a> enumerator that indicates the child device's level of hot-plug awareness.


## -remarks
The <b>ChildDeviceType</b> member of a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="..\dispmprt\ne-dispmprt-_dxgk_child_device_type.md">DXGK_CHILD_DEVICE_TYPE</a> enumerator that indicates type of the child device: <b>TypeVideoOutput</b> or <b>TypeOther</b>.

If a child device is of type <b>TypeVideoOutput</b>, the <b>Type.VideoOutput</b> member of its DXGK_CHILD_DESCRIPTOR structure is a DXGK_VIDEO_OUTPUT_CAPABILITIES structure.

If a child device is of type <b>TypeOther</b>, then <b>Type.Other.MustBeZero</b> must be set to zero.


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
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt-_dxgk_video_output_capabilities.md">DXGK_VIDEO_OUTPUT_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHILD_CAPABILITIES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

