---
UID: NS.d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
title: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the D3DKMTSignalSynchronizationObject2 function signals.
old-location: display\d3dkmt_signalsynchronizationobject2.htm
old-project: display
ms.assetid: a4bdafeb-310a-4ceb-966e-a1e3660fc5f2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2, D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
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

# D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure



## -description
<p>The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md">D3DKMTSignalSynchronizationObject2</a> function signals. </p>


## -syntax

````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 {
  D3DKMT_HANDLE        hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastContextCount;
  D3DKMT_HANDLE        BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  union {
    struct {
      UINT64 FenceValue;
    } Fence;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
    HANDLE CpuEventHandle;
#endif 
    UINT64 Reserved[8];
  };
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2;
````


## -struct-fields
<dl>

### -field <b>hContext</b>

<dd>
<p>[in] A kernel-mode handle to a context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.</p>
</dd>

### -field <b>ObjectCount</b>

<dd>
<p>[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. </p>
</dd>

### -field <b>ObjectHandleArray</b>

<dd>
<p>[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The D3DDDI_MAX_OBJECT_SIGNALED constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ns-d3dukmdt--d3dddicb-signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.</p>
</dd>

### -field <b>BroadcastContextCount</b>

<dd>
<p>[in] The number of additional contexts in the array that <b>BroadcastContext</b> specifies.</p>
</dd>

### -field <b>BroadcastContext</b>

<dd>
<p>[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the additional contexts to broadcast the event to. The D3DDDI_MAX_BROADCAST_CONTEXT constant, which is defined as 64, defines the maximum number of contexts that the OpenGL ICD can broadcast the event to.</p>
<p>The original context that the <b>hContext</b> member specifies and that owns the event is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the OpenGL ICD sends the event to the owning context (<b>hContext</b>) and broadcasts to that one additional context. </p>
</dd>

### -field <b>Fence</b>

<dd>
<p>A structure that contains information about a fence. The union in D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 can hold a Fence structure, which contains the following member:</p>
<dl>

### -field <b>FenceValue</b>

<dd>
<p>A 64-bit value that specifies the fence value to signal. </p>
</dd>
</dl>
</dd>

### -field <b>CpuEventHandle</b>

<dd>
<p>A handle to a CPU event that is to be signaled.</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>An array of 64-bit values that are reserved for future use. The union in D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 can hold this array. </p>
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
<p>D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system. </p>
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
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddicb-signalflags.md">D3DDDICB_SIGNALFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md">D3DKMTSignalSynchronizationObject2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
