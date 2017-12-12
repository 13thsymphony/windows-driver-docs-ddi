---
UID: NS.D3DUKMDT._D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
title: _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
author: windows-driver-content
description: Identifies attributes of a synchronization object.
old-location: display\d3dddi_synchronizationobject_flags.htm
old-project: display
ms.assetid: 57e5ea18-ccdd-40a7-9ff5-4d6b94908e7c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
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

# _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure



## -description
Identifies attributes of a synchronization object.



## -syntax

````
typedef struct _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS {
  union {
    struct {
      UINT Shared  :1;
      UINT NtSecuritySharing  :1;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3))
      UINT CrossAdapter  :1;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM2_0))
      UINT TopOfPipeline  :1;
      UINT NoSignal  :1;
      UINT NoWait  :1;
      UINT NoSignalMaxValueOnTdr  :1;
      UINT Reserved  :24;
#else 
      UINT Reserved  :28;
#endif 
#else 
      UINT Reserved  :29;
#endif 
      UINT D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS_RESERVED0  :1;
    };
    UINT Value;
  };
} D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS;
````


## -struct-fields

### -field Shared

A UINT value that specifies whether the synchronization object is shared.

If <b>Shared</b> is set to 1 (<b>TRUE</b>), the synchronization object is shared. If <b>Shared</b> is set to zero (<b>FALSE</b>), the synchronization object is not shared.

For more information, see the Remarks section.


### -field NtSecuritySharing

A UINT value that specifies whether the synchronization object is shared with an NT handle, meaning that it  does not have a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource.

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the synchronization object is shared but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource.

<div class="alert"><b>Note</b>  If <b>NtSecuritySharing</b> is set to 1,  <b>Shared</b>  must be set to 1.</div>
<div> </div>
For more information, see the Remarks section.

Supported starting with Windows 8.


### -field CrossAdapter

A UINT value that specifies whether the synchronization object is a shared cross-adapter object on a <a href="display.using_cross-adapter_resources_in_a_hybrid_system#definition_of_a_hybrid_system#definition_of_a_hybrid_system">hybrid system</a>.

If <b>CrossAdapter</b> is set to 1 (<b>TRUE</b>), the synchronization object is a shared cross-adapter object. If <b>CrossAdapter</b> is set to zero (<b>FALSE</b>), the synchronization object is not a shared cross-adapter object.

For more information, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.


### -field TopOfPipeline

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field TRUE

</td>
<td width="60%">
Specifies whether the synchronization object is signaled as soon as the contents of command buffer preceding it is entirely copied to the GPU pipeline, but not necessarily completed execution. This behavior allows reusing command buffers as soon as possible.

</td>
</tr>
<tr>
<td width="40%">

### -field FALSE

</td>
<td width="60%">
The synchronization object is signaled after the preceding command buffers completed execution.

</td>
</tr>
</table>
 

This value can only be set to 1 (<b>TRUE</b>) for monitored fence synchronization objects, and it should be set to zero (<b>FALSE</b>) for all other synchronization object types.

Supported starting with Windows 10.


### -field NoSignal

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field TRUE

</td>
<td width="60%">
Specifies the device this sync object is created or opened on can only submit wait commands for it. An attempt to submit a signal operation when this flag is set will return <b>STATUS_ACCESS_DENIED</b>.

</td>
</tr>
<tr>
<td width="40%">

### -field FALSE

</td>
<td width="60%">
The synchronization object can be signaled.

</td>
</tr>
</table>
 

This value can only be set to 1 (<b>TRUE</b>) for monitored fence synchronization objects, and it should be set to zero (<b>FALSE</b>) for all other synchronization object types.

Supported starting with Windows 10.


### -field NoWait

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field TRUE

</td>
<td width="60%">
Specifies the device this sync object is created or opened on can only submit signal commands for it. An attempt to submit a wait operation when this flag is set will return <b>STATUS_ACCESS_DENIED</b>.

</td>
</tr>
<tr>
<td width="40%">

### -field FALSE

</td>
<td width="60%">
The synchronization object can be waited on.

</td>
</tr>
</table>
 

This value can only be set to 1 (<b>TRUE</b>) for monitored fence synchronization objects, and it should be set to zero (<b>FALSE</b>) for all other synchronization object types.


This flag cannot be set simultaneously with <b>NoSignal</b> flag.


Supported starting with Windows 10.


### -field NoSignalMaxValueOnTdr

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field TRUE

</td>
<td width="60%">
Instructs the GPU scheduler to bypass the aforementioned signaling of the monitored fence to the maximum value in TDR cases.

</td>
</tr>
<tr>
<td width="40%">

### -field FALSE

</td>
<td width="60%">
The GPU scheduler will signal the monitored fence to the maximum value when a device that can potentially signal it is affected by the GPU reset (TDR).

</td>
</tr>
</table>
 

Supported starting with Windows 10.


### -field Reserved

This member is reserved and should be set to zero.


### -field Reserved

This member is reserved and should be set to zero.


### -field Reserved

This member is reserved and should be set to zero.


### -field D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS_RESERVED0

This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field Value

[in] A member in the union that is contained in <b>D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</b> that can hold one 32-bit value that identifies attributes of a synchronization object.


## -remarks
Objects to be shared by using the <a href="display.d3dkmtshareobjects">D3DKMTShareObjects</a> function must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <a href="display.d3dkmt_createallocationflags">D3DKMT_CREATEALLOCATIONFLAGS</a>, <a href="display.d3dkmt_createkeyedmutex2_flags">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <b>D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</b> structures.

Drivers should follow these guidelines on <b>D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</b> flags:


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS is supported beginning with the Windows 7 operating system. 

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
<a href="display.d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>
</dt>
<dt>
<a href="display.d3dkmt_createallocationflags">D3DKMT_CREATEALLOCATIONFLAGS</a>
</dt>
<dt>
<a href="display.d3dkmt_createkeyedmutex2_flags">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>
</dt>
<dt>
<a href="display.d3dkmtshareobjects">D3DKMTShareObjects</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

