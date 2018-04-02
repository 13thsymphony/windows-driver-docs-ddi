---
UID: NS:d3dkmthk._D3DKMT_CREATEALLOCATIONFLAGS
title: "_D3DKMT_CREATEALLOCATIONFLAGS"
author: windows-driver-content
description: The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the D3DKMTCreateAllocation function.
old-location: display\d3dkmt_createallocationflags.htm
old-project: display
ms.assetid: ddcb8222-808b-4dfe-9303-a588b3522ebe
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CREATEALLOCATIONFLAGS, D3DKMT_CREATEALLOCATIONFLAGS structure [Display Devices], OpenGL_Structs_0b22984b-feef-4975-b7d9-596427c82b2b.xml, _D3DKMT_CREATEALLOCATIONFLAGS, d3dkmthk/D3DKMT_CREATEALLOCATIONFLAGS, display.d3dkmt_createallocationflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATEALLOCATIONFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CREATEALLOCATIONFLAGS
---

# _D3DKMT_CREATEALLOCATIONFLAGS structure
The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546807">D3DKMTCreateAllocation</a> function.

## Syntax
```
typedef struct _D3DKMT_CREATEALLOCATIONFLAGS {
  UINT  : 1  CreateResource;
  UINT  : 1  CreateShared;
  UINT  : 1  NonSecure;
  UINT  : 1  CreateProtected;
  UINT  : 1  RestrictSharedAccess;
  UINT  : 1  ExistingSysMem;
  UINT  : 1  NtSecuritySharing;
  UINT  : 1  ReadOnly;
  UINT  : 1  CreateWriteCombined;
  UINT  : 1  CreateCached;
  UINT  : 1  SwapChainBackBuffer;
  UINT  : 1  CrossAdapter;
  UINT  : 1  OpenCrossAdapter;
  UINT  : 1  PartialSharedCreation;
  UINT  : 1  Zeroed;
  UINT  : 1  WriteWatch;
  UINT  : 1  StandardAllocation;
  UINT  : 1  ExistingSection;
#if ...
  UINT  : 14 Reserved;
#elif
  UINT  : 16 Reserved;
#elif
  UINT  : 20 Reserved;
#else
  UINT  : 25 Reserved;
#endif
} D3DKMT_CREATEALLOCATIONFLAGS;
```

## Members


`CreateResource`

A UINT value that specifies whether to create a device-specific resource.

If you set <b>CreateShared</b>, you must also set <b>CreateResource</b>.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

`CreateShared`

A UINT value that specifies whether to create a resource shared across all devices. 

If you set <b>CreateShared</b>, you must also set <b>CreateResource</b>.

For more information on using <b>CreateShared</b>, see the Remarks section.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).

`NonSecure`

A UINT value that specifies whether to create an allocation that can be opened by any process. If <b>NonSecure</b> is set, secure and non-secure processes can open the allocation.

Setting this member is equivalent to setting the third bit of a 32-bit value (0x00000004).

`CreateProtected`

This member is reserved and should be set to zero. Setting this member is equivalent to setting the fourth bit of a 32-bit value (0x00000008).

Supported starting with Windows 7.

`RestrictSharedAccess`

A UINT value that specifies whether to create a resource shared across all devices but with some restrictions.

Setting this member is equivalent to setting the fifth bit of a 32-bit value (0x00000010).

Supported starting with Windows 7.

`ExistingSysMem`

This member is reserved and should be set to zero. Setting this member is equivalent to setting the sixth bit of a 32-bit value (0x00000020).

Supported starting with Windows 7.

`NtSecuritySharing`

A UINT value that specifies whether the allocation is shared with an NT handle, meaning that it  does not have a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource.

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the allocation is shared using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a> function but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource.

<div class="alert"><b>Note</b>  If <b>NtSecuritySharing</b> is set to 1,  <b>CreateShared</b>  must be set to 1.</div>
<div> </div>
For more information on using <b>NtSecuritySharing</b>, see the Remarks section.

Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000040).

Supported starting with Windows 8.

`ReadOnly`

A UINT value that specifies whether the allocation can only be read from.

Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000080).

Supported starting with Windows 8.

`CreateWriteCombined`

This member is reserved and should be set to zero. Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.

`CreateCached`

This member is reserved and should be set to zero. Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000200).

Supported starting with Windows 8.

`SwapChainBackBuffer`

This member is reserved and should be set to zero. Setting this member is equivalent to setting the seventh bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.

`CrossAdapter`



`OpenCrossAdapter`



`PartialSharedCreation`



`Zeroed`



`WriteWatch`



`StandardAllocation`



`ExistingSection`



## Remarks
Objects to be shared by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a> function must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <b>D3DKMT_CREATEALLOCATIONFLAGS</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh780254">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff544662">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structures.

Drivers should follow these guidelines on <b>D3DKMT_CREATEALLOCATIONFLAGS</b> sharing flags:

<ul>
<li>If the allocation is not shared, set both  <b>CreateShared</b> and <b>NtSecuritySharing</b> to 0.</li>
<li>If the allocation is shared with a <b>D3DKMT_HANDLE</b> data type, set <b>CreateShared</b> = 1 and <b>NtSecuritySharing</b> = 0.</li>
<li>If the allocation is shared with an NT handle to the process (and without a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource), set <b>CreateShared</b> = 1 and <b>NtSecuritySharing</b> = 1.</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546807">D3DKMTCreateAllocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547798">D3DKMT_CREATEALLOCATION</a>