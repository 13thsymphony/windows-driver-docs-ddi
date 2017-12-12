---
UID: NS.D3DUKMDT._D3DDDI_SYNCHRONIZATIONOBJECTINFO2
title: _D3DDDI_SYNCHRONIZATIONOBJECTINFO2
author: windows-driver-content
description: The D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure contains information about a second-generation synchronization object.
old-location: display\d3dddi_synchronizationobjectinfo2.htm
old-project: display
ms.assetid: dc1c6a67-320c-41f8-91ad-cdbcde191a81
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDI_SYNCHRONIZATIONOBJECTINFO2, D3DDDI_SYNCHRONIZATIONOBJECTINFO2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_SYNCHRONIZATIONOBJECTINFO2 is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_SYNCHRONIZATIONOBJECTINFO2
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
---

# _D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure



## -description
The <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> structure contains information about a second-generation synchronization object.



## -syntax

````
typedef struct _D3DDDI_SYNCHRONIZATIONOBJECTINFO2 {
  D3DDDI_SYNCHRONIZATIONOBJECT_TYPE  Type;
  D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS Flags;
  union {
    struct {
      BOOL InitialState;
    } SynchronizationMutex;
    struct {
      UINT MaxCount;
      UINT InitialCount;
    } Semaphore;
    struct {
      UINT64 FenceValue;
    } Fence;
    struct {
      HANDLE Event;
    } CPUNotification;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM2_0))
    struct {
      UINT64                 InitialFenceValue;
      VOID                   *FenceValueCPUVirtualAddress;
      D3DGPU_VIRTUAL_ADDRESS FenceValueGPUVirtualAddress;
      UINT                   EngineAffinity;
    } MonitoredFence;
#endif 
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM2_2))
    struct {
      D3DKMT_HANDLE                  hAdapter;
      D3DDDI_VIDEO_PRESENT_TARGET_ID 	VidPnTargetID;
      UINT64                         Time;
      VOID                           *FenceValueCPUVirtualAddress;
      D3DGPU_VIRTUAL_ADDRESS         FenceValueGPUVirtualAddress;
      UINT                           EngineAffinity;
    } PeriodicMonitoredFence;
    struct {
      UINT64 Reserved[8];
    } Reserved;
  };
  D3DKMT_HANDLE                      SharedHandle;
} D3DDDI_SYNCHRONIZATIONOBJECTINFO2;
````


## -struct-fields

### -field Type

[in] A value of type <a href="display.d3dddi_synchronizationobject_type">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a> that indicates the type of synchronization object.


### -field Flags

[in] A <a href="display.d3dddi_synchronizationobject_flags">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structure that specifies, in bit-field flags, attributes of the synchronization object. 


### -field SynchronizationMutex

A structure that contains information about a synchronization mutex. If the <b>Type</b> member is equal to <b>D3DDDI_SYNCHRONIZATION_MUTEX</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>SynchronizationMutex</b> structure, which contains the following member:


### -field InitialState

A Boolean value that indicates whether the synchronization mutex is initially owned by an object. A value of <b>TRUE</b> indicates that the mutex is owned; <b>FALSE</b> indicates that the mutex is not owned. 

</dd>
</dl>

### -field Semaphore

A structure that contains information about a semaphore. If the <b>Type</b> member is equal to <b>D3DDDI_SEMAPHORE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>Semaphore</b> structure, which contains the following members:


### -field MaxCount

The maximum number of events that an object can be waiting for. 


### -field InitialCount

The initial number of events that an object is waiting for. 

</dd>
</dl>

### -field Fence

A structure that contains information about a fence. If the <b>Type</b> member is equal to <b>D3DDDI_FENCE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>Fence</b> structure, which contains the following member:


### -field FenceValue

A 64-bit value that specifies the initial fence value. 

</dd>
</dl>

### -field CPUNotification

A structure that contains information about a CPU notification. If the <b>Type</b> member is equal to <b>D3DDDI_CPU_NOTIFICATION</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>CPUNotification</b> structure, which contains the following member:


### -field Event

The handle to the CPU notification event. 

</dd>
</dl>

### -field MonitoredFence

A structure that contains information about a monitored fence. If the <b>Type</b> member is equal to <b>D3DDDI_MONITORED_FENCE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>MonitoredFence</b> structure.

Supported starting with Windows 10.


### -field InitialFenceValue

[in] A 64-bit value that specifies the initial fence value. 

Supported starting with Windows 10.


### -field FenceValueCPUVirtualAddress

[out] A read-only mapping of the fence value for the CPU. This is a user mode address readable from the process that created the monitored fence object. For 32 bit platforms that support 64 bit atomic reads via methods such as <code>InterlockedCompareExchange64(pointer,0,0)</code>, the mapping will be made read-write instead of read-only to avoid an access violation during the interlocked operation. Depending on the value of <b>No64BitAtomics</b> cap, this address points to either a 32 bit or a 64 bit underlying value.

Supported starting with Windows 10.


### -field FenceValueGPUVirtualAddress

[out] A read-write mapping of the fence value for the GPU. A driver can signal a new fence value by inserting a GPU write command for this address into a command buffer, and the DirectX graphics kernel will unblock waiters for this fence object value. Depending on the value of <b>No64BitAtomics</b> cap, this address points to either a 32 bit or a 64 bit underlying value.

Supported starting with Windows 10.


### -field EngineAffinity

[in] A bit field, where each bit position (starting from zero) defines a physical adapter index in an link display adapter (LDA) link where the GPU virtual address will be committed. Zero means that the GPU virtual address will be committed to all physical adapters.

Supported starting with Windows 10.

</dd>
</dl>

### -field PeriodicMonitoredFence

A structure that contains information about a periodic monitored fence. If the <b>Type</b> member is equal to <b>D3DDDI_PERIODIC_MONITORED_FENCE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>MonitoredFence</b> structure.

Supported starting with Windows 10.


### -field hAdapter

[in] A handle to the adapter associated with VidPnSourceID


### -field 	VidPnTargetID

[out] The output ID that the compositor wishes to receive notifications for.


### -field Time

[out] Represents an offset before the VSync (time of VSync – Time parameter). The Time value may not be longer than a VSync interval (1 / DisplayModeRefresh). Time is specified in units of 100ns.


### -field FenceValueCPUVirtualAddress

[in] Read-only mapping of the fence value for the CPU


### -field FenceValueGPUVirtualAddress

[in] Read-only mapping of the fence value for the GPU


### -field EngineAffinity

[in] Defines physical adapters where the GPU VA will be mapped

</dd>
</dl>

### -field Reserved

A structure that is reserved for future use. This structure contains the following member:


### -field Reserved

An array of 64-bit values that are reserved for future use.

</dd>
</dl>

### -field SharedHandle

[out] A handle to the shared synchronization object if a shared handle currently exists. The shared handle is returned from the call to the <a href="display.d3dkmtcreatesynchronizationobject2">D3DKMTCreateSynchronizationObject2</a> function. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
<b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> is supported beginning with the Windows 7 operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="display.d3dddi_synchronizationobject_flags">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a>
</dt>
<dt>
<a href="display.d3dddi_synchronizationobject_type">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a>
</dt>
<dt>
<a href="display.d3dkmt_createsynchronizationobject2">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a>
</dt>
<dt>
<a href="display.d3dkmtcreatesynchronizationobject2">D3DKMTCreateSynchronizationObject2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

