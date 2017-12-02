---
UID: NS.d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
title: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
author: windows-driver-content
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 is used with D3DKMTSignalSynchronizationObjectFromGpu2 to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromgpu2.htm
old-project: display
ms.assetid: 3F9A7BBE-BFC2-47B9-856A-0B6930717A36
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
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
req.iface: 
---

# D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure



## -description
<p><b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md">D3DKMTSignalSynchronizationObjectFromGpu2</a> to signal a monitored fence.</p>


## -syntax

````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 {
  UINT                 ObjectCount;
  const D3DKMT_HANDLE  *ObjectHandleArray;
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastContextCount;
  const D3DKMT_HANDLE  *BroadcastContextArray;
  union {
    UINT64       FenceValue;
    HANDLE       CpuEventHandle;
    const UINT64 *MonitoredFenceValueArray;
    UINT64       Reserved[8];
  };
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2;
````


## -struct-fields
<dl>

### -field ObjectCount

<dd>
<p>[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.</p>
</dd>

### -field ObjectHandleArray

<dd>
<p>[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.</p>
</dd>

### -field Flags

<dd>
<p>[in] A <a href="..\d3dukmdt\ns-d3dukmdt--d3dddicb-signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.</p>
</dd>

### -field BroadcastContextCount

<dd>
<p>[in] The number of contexts this signal operation will be broadcast to.</p>
</dd>

### -field BroadcastContextArray

<dd>
<p>[in] An array of kernel-mode handles to the context streams in which a signal for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted. The synchronization events are considered signaled only when all broadcast contexts reach the signal insertion point.</p>
</dd>

### -field FenceValue

<dd>
<p>[in] A 64-bit value that specifies the current fence value of the GPU synchronization object. This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>.</p>
</dd>

### -field CpuEventHandle

<dd>
<p>[in] The handle of an event object that will be signaled when the signal command is processed. This member must be set only when <b>Flags.EnqueueCpuEvent</b> is specified.</p>
</dd>

### -field MonitoredFenceValueArray

<dd>
<p>[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md">D3DKMTSignalSynchronizationObjectFromGpu2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
