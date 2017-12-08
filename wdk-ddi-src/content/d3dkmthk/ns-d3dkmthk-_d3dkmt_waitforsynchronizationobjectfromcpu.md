---
UID: NS.D3DKMTHK._D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
author: windows-driver-content
description: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTWaitForSynchronizationObjectFromCpu to wait for a monitored fence to reach a certain value.
old-location: display\d3dkmt_waitforsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: 76091965-D87B-4429-85A8-EC8085C773D7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU, D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
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
req.alt-api: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
req.alt-loc: D3dkmthk.h
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

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure



## -description
<b>D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="display.d3dkmtwaitforsynchronizationobjectfromcpu">D3DKMTWaitForSynchronizationObjectFromCpu</a> to wait for a monitored fence to reach a certain value.


## -syntax

````
typedef struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU {
  D3DKMT_HANDLE                                    hDevice;
  UINT                                             ObjectCount;
  const D3DKMT_HANDLE                              *ObjectHandleArray;
  const UINT64                                     *FenceValueArray;
  HANDLE                                           hAsyncEvent;
  D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS Flags;
} D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU;
````


## -struct-fields

### -field hDevice

[in] The device handle to wait on.

### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>. 

### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to wait for.

### -field FenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each corresponding to an object in the <b>ObjectHandleArray</b>.

### -field hAsyncEvent

[in] When not <b>NULL</b>, specifies the event to be signaled when the wait condition is satisfied. When <b>NULL</b>, the call will not return until the wait condition is satisfied.

### -field Flags

[in] A <a href="display.d3dddi_waitforsynchronizationobjectfromcpu_flags">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a> structure describing the operation.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field WaitAny
### -field FALSE

</td>
<td width="60%">
The wait condition is considered to be satisfied when all input synchronization objects are signaled to the corresponding input fence values or greater.
</td>
</tr>
<tr>

### -field WaitAny
### -field TRUE

</td>
<td width="60%">
The wait condition is considered to be satisfied when any of the input synchronization objects is signaled to the corresponding input fence value or greater.
</td>
</tr>
</table>
 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="display.d3dkmtwaitforsynchronizationobjectfromcpu">D3DKMTWaitForSynchronizationObjectFromCpu</a>
</dt>
<dt>
<a href="display.d3dddi_waitforsynchronizationobjectfromcpu_flags">D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
