---
UID: NS.d3dkmddi._DXGK_OPENALLOCATIONINFO
title: DXGK_OPENALLOCATIONINFO
author: windows-driver-content
description: The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the DxgkDdiOpenAllocation function associates.
old-location: display\dxgk_openallocationinfo.htm
ms.assetid: e23b7e4e-e670-4421-aa2f-4389a74a7d6d
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_OPENALLOCATIONINFO
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
ms.keywords: DXGK_OPENALLOCATIONINFO, DXGK_OPENALLOCATIONINFO
req.iface: 
---

# DXGK_OPENALLOCATIONINFO structure



## -description
<p>The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function associates. </p>


## -syntax

````
typedef struct _DXGK_OPENALLOCATIONINFO {
  D3DKMT_HANDLE hAllocation;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
  HANDLE        hDeviceSpecificAllocation;
} DXGK_OPENALLOCATIONINFO;
````


## -struct-fields
<dl>

### -field <b>hAllocation</b>

<dd>
<p>[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the nondevice-specific allocation that the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function created. The Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned this handle for the allocation.</p>
</dd>

### -field <b>pPrivateDriverData</b>

<dd>
<p>[in/out] A pointer to a block of private data that is passed between the user-mode display driver and the display miniport driver. This block of private data is the same allocation-specific data that is passed in the <b>pPrivateDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a> structure in the call to the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function. The display miniport driver's <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function can modify this block of private data if the <b>Create</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a> structure. The user-mode display driver can access modifications to the block of private data.</p>
</dd>

### -field <b>PrivateDriverDataSize</b>

<dd>
<p>[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.</p>
</dd>

### -field <b>hDeviceSpecificAllocation</b>

<dd>
<p>[out] A handle to the device-specific allocation that corresponds to the non device-specific allocation that <b>hAllocation</b> specifies. The display miniport driver must set <b>hDeviceSpecificAllocation</b> to a handle value that it can use to refer to its private tracking structure for the allocation.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557609">DXGKARG_OPENALLOCATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_OPENALLOCATIONINFO structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
