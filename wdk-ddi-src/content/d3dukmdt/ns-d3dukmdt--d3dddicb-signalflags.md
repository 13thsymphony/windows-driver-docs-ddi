---
UID: NS.d3dukmdt._D3DDDICB_SIGNALFLAGS
title: D3DDDICB_SIGNALFLAGS
author: windows-driver-content
description: The D3DDDICB_SIGNALFLAGS structure describes signaling behavior in a call to the pfnSignalSynchronizationObjectCb or pfnSignalSynchronizationObject2Cb functions.
old-location: display\d3dddicb_signalflags.htm
old-project: display
ms.assetid: 1efe98c4-021b-4312-bbcc-52267e528b5f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDICB_SIGNALFLAGS, D3DDDICB_SIGNALFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_SIGNALFLAGS
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
req.iface: 
---

# D3DDDICB_SIGNALFLAGS structure



## -description
<p>The D3DDDICB_SIGNALFLAGS structure describes signaling behavior in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> functions.</p>


## -syntax

````
typedef struct _D3DDDICB_SIGNALFLAGS {
  union {
    struct {
      UINT SignalAtSubmission  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
      UINT EnqueueCpuEvent  :1;
      UINT Reserved  :30;
#else 
      UINT Reserved  :31;
#endif 
    };
    UINT Value;
  };
} D3DDDICB_SIGNALFLAGS;
````


## -struct-fields
<dl>

### -field <b>SignalAtSubmission</b>

<dd>
<p>A UINT value that specifies whether a context should signal synchronization objects when the previously queued packet is submitted rather than completed (which is the default behavior).</p>
<p>Setting this member is equivalent to setting the first bit of the 32-bit  <b>Value</b> member (0x00000001).</p>
</dd>

### -field <b>EnqueueCpuEvent</b>

<dd>
<p>A UINT value that modifies the behavior of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function. When this member is set,  the event specified by the <b>CpuEventHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a> structure is signaled when all contexts specified in  <b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</b>  process the signal command.</p>
<p>If this member is set,  members of  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a>  structure that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function's <i>pData</i> parameter points to are restricted as follows:</p>
<ul>
<li><b>ObjectCount</b> must be zero.</li>
<li><b>CpuEventHandle</b> must be a valid event handle.</li>
</ul>
<p>Setting this member is equivalent to setting the second bit of the 32-bit  <b>Value</b> member (0x00000002).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero.</p>
<p>Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.</p>
</dd>

### -field <b>Value</b>

<dd>
<p>A member in the union that is contained in D3DDDICB_SIGNALFLAGS that can hold one 32-bit value that identifies signaling behavior.</p>
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
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544274">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SIGNALFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
