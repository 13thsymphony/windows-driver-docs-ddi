---
UID: NS.D3DUMDDI._DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
title: _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure describes private stream-state data that is used to query the inverse telecine statistics from the driver.
old-location: display\dxvahdddi_stream_state_private_ivtc_data.htm
old-project: display
ms.assetid: d882a13e-cc07-4e82-857e-499bc397517e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA, DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA
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

# _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure



## -description
The DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure describes private stream-state data that is used to query the inverse telecine statistics from the driver. 



## -syntax

````
typedef struct _DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA {
  BOOL Enable;
  UINT ITelecineFlags;
  UINT Frames;
  UINT InputField;
} DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA;
````


## -struct-fields

### -field Enable

[in/out] A Boolean value that indicates whether to capture the statistics is enabled. By enabling the capture of statistics, the driver resets all the statistics data to zero. The default value is <b>FALSE</b>, which indicates that capturing the statistics is disabled. 


### -field ITelecineFlags

[out] One of the following DXVAHDDDI_ITELECINE_CAPS enumeration values that indicates the telecine type that the driver detected while reversing the telecined frames.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_32 (0x1)

</td>
<td>
The driver can perform reverse 3:2 telecine, NTSC(60i) -&gt; Film(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_22 (0x2)

</td>
<td>
The driver can perform reverse 2:2 telecine, PAL(50i) -&gt; Film(25p:4% faster) and NTSC(60i) -&gt; CG(30p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_2224 (0x4)

</td>
<td>
The driver can perform reverse 2:2:2:4 telecine, NTSC(60i) -&gt; DVCAM(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_2332 (0x8)

</td>
<td>
The driver can perform reverse 2:3:3:2 telecine, NTSC(60i) -&gt; DVCAM(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_32322 (0x10)

</td>
<td>
The driver can perform reverse 3:2:3:2:2 telecine, NTSC(60i) -&gt; Film(25p:4% faster).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_55 (0x20)

</td>
<td>
The driver can perform reverse 5:5 telecine, NTSC(60i) -&gt; Animation(12p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_64 (0x40)

</td>
<td>
The driver can perform reverse 6:4 telecine, NTSC(60i) -&gt; Animation(12p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_87 (0x80)

</td>
<td>
The driver can perform reverse 8:7 telecine, NTSC(60i) -&gt; Anime(8p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_222222222223 (0x100)

</td>
<td>
The driver can perform reverse 2:2:2:2:2:2:2:2:2:2:2:3 telecine, PAL(50i) -&gt; Film(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_OTHER (0x80000000)

</td>
<td>
The driver can perform reverse non-standard telecine.

</td>
</tr>
</table>
 


### -field Frames

[out] The number of consecutive frames that the driver detects for the telecined frames. 


### -field InputField

[out] The last field number of the input stream that was processed (so far). The driver updates this member after the driver has processed the input field that is specified in the <b>InputFrameOrField</b> member of the <a href="display.dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a> structure. 


## -remarks
The DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC GUID is set in the <b>Guid</b> member of the <a href="display.dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate.md">GetVideoProcessStreamStatePrivate</a> function is called to query the inverse telecine statistics from the driver.

When an application de-interlaces an interlaced stream, the driver might inverse the telecined frames. If the driver supports inverse telecine statistics, the application can query the statistics data.

The playback application can dynamically switch the frame rate converter as described in the following scenario:

The application enables the inverse telecine statistics. 

The application begins to de-interlace the interlaced fields to the progressive frames. 

At some point, the application queries the statistics and determines the streams are telecined frames.

The application enables the custom frame rate in order to output the frames at the original content frame rate (for example, 60i -&gt; 24p). 

The application continues to query the statistics to determine if the frames are changed (for example, progressive or interlaced).


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA is supported beginning with the Windows 7 operating system.

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
<a href="display.dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_PRIVATE_IVTC_DATA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

