---
UID: NS.d3dkmddi._DXGKARG_COLLECTDBGINFO
title: DXGKARG_COLLECTDBGINFO
author: windows-driver-content
description: The DXGKARG_COLLECTDBGINFO structure describes information for a debug report.
old-location: display\dxgkarg_collectdbginfo.htm
old-project: display
ms.assetid: f0dd72b5-9ab4-4511-b913-b0e456ea8950
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGKARG_COLLECTDBGINFO, DXGKARG_COLLECTDBGINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_COLLECTDBGINFO
req.alt-loc: d3dkmddi.h
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
req.iface: 
---

# DXGKARG_COLLECTDBGINFO structure



## -description
<p>The DXGKARG_COLLECTDBGINFO structure describes information for a debug report.</p>


## -syntax

````
typedef struct _DXGKARG_COLLECTDBGINFO {
  UINT                       Reason;
  VOID                       *pBuffer;
  SIZE_T                     BufferSize;
  DXGKARG_COLLECTDBGINFO_EXT *pExtension;
} DXGKARG_COLLECTDBGINFO;
````


## -struct-fields
<dl>

### -field Reason

<dd>
<p>[in] The <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug-check code</a> for which to return debug information in the buffer that <b>pBuffer</b> points to. These are possible values:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VIDEO_TDR_TIMEOUT_DETECTED"></a><a id="video_tdr_timeout_detected"></a><dl>

### -field VIDEO_TDR_TIMEOUT_DETECTED


### -field 0x117

</dl>
</td>
<td width="60%">
<p>A <a href="display.dxgkddiresetengine">DxgkDdiResetEngine</a> operation has reset a logical adapter.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="VIDEO_ENGINE_TIMEOUT_DETECTED"></a><a id="video_engine_timeout_detected"></a><dl>

### -field VIDEO_ENGINE_TIMEOUT_DETECTED


### -field 0x141

</dl>
</td>
<td width="60%">
<p>A <a href="display.dxgkddiresetengine">DxgkDdiResetEngine</a> operation has reset one or more nodes within a physical adapter.</p>
<p>Available starting in Windows 8.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field pBuffer

<dd>
<p>[out] A pointer to a buffer that receives the debug information that <b>Reason</b> specifies.</p>
</dd>

### -field BufferSize

<dd>
<p>[in] The maximum size, in bytes, to copy to the buffer that <b>pBuffer</b> points to.</p>
</dd>

### -field pExtension

<dd>
<p>[out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-collectdbginfo-ext.md">DXGKARG_COLLECTDBGINFO_EXT</a> structure that is allocated by the operating system and that the driver optionally populates with debug extension information.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-collectdbginfo-ext.md">DXGKARG_COLLECTDBGINFO_EXT</a>
</dt>
<dt>
<a href="display.dxgkddicollectdbginfo">DxgkDdiCollectDbgInfo</a>
</dt>
<dt>
<a href="display.dxgkddiresetengine">DxgkDdiResetEngine</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_COLLECTDBGINFO structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
