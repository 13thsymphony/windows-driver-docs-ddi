---
UID: NS.D3DKMDDI._DXGK_VIDMMCAPS
title: _DXGK_VIDMMCAPS
author: windows-driver-content
description: The DXGK_VIDMMCAPS structure identifies the video memory management capabilities that a display miniport driver can support.
old-location: display\dxgk_vidmmcaps.htm
old-project: display
ms.assetid: c3df50a0-2388-4760-b6e2-ef6af650d0e2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_VIDMMCAPS, DXGK_VIDMMCAPS
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
req.alt-api: DXGK_VIDMMCAPS
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
---

# _DXGK_VIDMMCAPS structure



## -description
The <b>DXGK_VIDMMCAPS</b> structure identifies the video memory management capabilities that a display miniport driver can support.



## -syntax

````
typedef struct _DXGK_VIDMMCAPS {
  union {
    struct {
      UINT OutOfOrderLock  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
      UINT DedicatedPagingEngine  :1;
      UINT PagingEngineCanSwizzle  :1;
      UINT SectionBackedPrimary  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
      UINT CrossAdapterResource  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
      UINT VirtualAddressingSupported  :1;
      UINT GpuMmuSupported  :1;
      UINT IoMmuSupported  :1;
      UINT ReplicateGdiContent  :1;
      UINT Reserved  :23;
#else 
      UINT Reserved  :27;
#endif 
#else 
      UINT Reserved  :28;
#endif 
#else 
      UINT Reserved  :31;
#endif 
    };
    UINT Value;
  };
  UINT PagingNode;
} DXGK_VIDMMCAPS;
````


## -struct-fields

### -field OutOfOrderLock

Specifies whether the driver can lock allocation instances other than the latest instance. The driver typically sets this value for DDI threading and load balancing if a DDI thread must lock a vertex buffer that an application thread had previously locked and discarded. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001). 


### -field DedicatedPagingEngine

This member is reserved and should be set to zero.


### -field PagingEngineCanSwizzle

This member is reserved and should be set to zero.


### -field SectionBackedPrimary

Specifies whether the driver supports section-backed primary allocations.

Supported starting with Windows 8.


### -field CrossAdapterResource

Specifies whether the driver supports cross-adapter resources in a <a href="display.using_cross-adapter_resources_in_a_hybrid_system#definition_of_a_hybrid_system#definition_of_a_hybrid_system">hybrid system</a>.

Supported starting with Windows 8.1.


### -field VirtualAddressingSupported

Specifies whether the driver supports virtual memory addressing.

To express support for GPU virtual memory addressing, the driver should set the <b>VirtualAddressingSupported</b> cap and <b>GpuMmuSupported</b> or <b>IoMmuSupported</b> caps.
<b>GpuMmuSupported</b> and <b>IoMmuSupported</b> cannot be set at the same time.


Supported starting with Windows 10.


### -field GpuMmuSupported

Specifies whether the adapter supports the <i>GpuMmu</i> model. An adapter cannot support the <i>GpuMmu</i> and the <i>IoMmu</i> models on different engines at the same time.

Supported starting with Windows 10.


### -field IoMmuSupported

Specifies whether the adapter supports the <i>IoMmu</i> model. An adapter cannot support the <i>GpuMmu</i> and the <i>IoMmu</i> models on different engines at the same time.

Supported starting with Windows 10.


### -field ReplicateGdiContent

Specifies whether the adapter supports the replication of GDI content.

Supported starting with Windows 10.


### -field Reserved

This member is reserved and should be set to zero.


### -field Reserved

This member is reserved and should be set to zero.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (after setting <b>OutOfOrderLock</b>) of the <b>Value</b> member to zeros.

Note that this version of the <b>Reserved</b> member is available only if DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (after setting <b>OutOfOrderLock</b>) of the <b>Value</b> member to zeros. 

Note that this version of the <b>Reserved</b> member is available only if DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7.


### -field Value


       A 32-bit value.
      


### -field PagingNode

The zero-based index of the node to use for paging operations. If the driver does not set the <b>MultiEngineAware</b> bit-field member of the <b>SchedulingCaps</b> member of the <a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure, the DirectX graphics kernel subsystem ignores the setting of <b>PagingNode</b>. 


## -remarks


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_VIDMMCAPS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

