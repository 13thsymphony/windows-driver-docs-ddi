---
UID: NC.video.PINT10_FREE_BUFFER
title: PINT10_FREE_BUFFER
author: windows-driver-content
description: The Int10FreeBuffer function frees a buffer previously allocated by Int10AllocateBuffer.
old-location: display\int10freebuffer.htm
old-project: display
ms.assetid: feb7dd98-8c44-405e-8e98-ffd6246cf0ee
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Int10FreeBuffer
req.alt-loc: video.h
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
req.product: Windows 10 or later.
---

# PINT10_FREE_BUFFER callback



## -description
<p>The <i>Int10FreeBuffer</i> function frees a buffer previously allocated by <i>Int10AllocateBuffer</i>.</p>


## -prototype

````
PINT10_FREE_BUFFER Int10FreeBuffer;

VP_STATUS Int10FreeBuffer(
  _In_ PVOID  Context,
  _In_ USHORT Seg,
  _In_ USHORT Off
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> returns.</p>
</dd>

### -param <i>Seg</i> [in]

<dd>
<p>Specifies the segment address of the buffer to be freed.</p>
</dd>

### -param <i>Off</i> [in]

<dd>
<p>Specifies the offset within the segment indicated by the <i>Seg</i> parameter.</p>
</dd>
</dl>

## -returns
<p>The <i>Int10FreeBuffer</i> function returns NO_ERROR upon success. Otherwise, the function returns an appropriate error code.</p>

## -remarks
<p>The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure.</p>

<p>The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PINT10_FREE_BUFFER callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
