---
UID: NS.D3DKMDT._D3DKMDT_VIDPN_SOURCE_MODE
title: _D3DKMDT_VIDPN_SOURCE_MODE
author: windows-driver-content
description: The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.
old-location: display\d3dkmdt_vidpn_source_mode.htm
old-project: display
ms.assetid: 763db6bb-8991-406d-a1d4-8ad50e32fee1
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMDT_VIDPN_SOURCE_MODE, D3DKMDT_VIDPN_SOURCE_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_SOURCE_MODE
req.alt-loc: d3dkmdt.h
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

# _D3DKMDT_VIDPN_SOURCE_MODE structure



## -description
The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.



## -syntax

````
typedef struct _D3DKMDT_VIDPN_SOURCE_MODE {
  D3DKMDT_VIDEO_PRESENT_SOURCE_MODE_ID Id;
  D3DKMDT_VIDPN_SOURCE_MODE_TYPE       Type;
  union {
    D3DKMDT_GRAPHICS_RENDERING_FORMAT Graphics;
    D3DKMDT_TEXT_RENDERING_FORMAT     Text;
  } Format;
} D3DKMDT_VIDPN_SOURCE_MODE;
````


## -struct-fields

### -field Id

An integer that identifies the source mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>.


### -field Type

A <a href="display.d3dkmdt_vidpn_source_mode_type">D3DKMDT_VIDPN_SOURCE_MODE_TYPE</a> enumerator that indicates the mode type: graphics or text.


### -field Format

A union that contains information about either the graphics rendering format or the text format in the following members. 



### -field Graphics

A <a href="display.d3dkmdt_graphics_rendering_format">D3DKMDT_GRAPHICS_RENDERING_FORMAT</a> structure that contains information about the graphics rendering format (for example, primary surface size and pixel format). This member is meaningful only if the <b>Type</b> member is equal to D3DKMDT_RMT_GRAPHICS.


### -field Text

A <a href="display.d3dkmdt_text_rendering_format">D3DKMDT_TEXT_RENDERING_FORMAT</a> enumerator that indicates the text format. This member is meaningful only if the <b>Type</b> member is equal to D3DKMDT_RMT_TEXT.

</dd>
</dl>

## -remarks
For more information about video present sources and VidPN source modes, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a> and <a href="https://msdn.microsoft.com/f1aa6277-7af6-4ba0-8ff1-d562f7029540">Enumerating Cofunctional VidPN Source and Target Modes</a>.


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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.vidpn_source_mode_set_interface">VidPN Source Mode Set Interface</a>
</dt>
<dt>
<a href="display.d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>
</dt>
<dt>
<a href="display.d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_SOURCE_MODE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

