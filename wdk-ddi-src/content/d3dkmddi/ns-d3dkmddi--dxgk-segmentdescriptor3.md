---
UID: NS.d3dkmddi._DXGK_SEGMENTDESCRIPTOR3
title: DXGK_SEGMENTDESCRIPTOR3
author: windows-driver-content
description: Contains information about a driver-supported segment that is composed of both BIOS-reserved memory (which is purged during a transition to a low-power state) and driver-reserved memory.
old-location: display\dxgk_segmentdescriptor3.htm
old-project: display
ms.assetid: c304fd47-a9c7-46bd-819f-6751eba25459
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_SEGMENTDESCRIPTOR3, DXGK_SEGMENTDESCRIPTOR3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_SEGMENTDESCRIPTOR3
req.alt-loc: D3dkmddi.h
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
---

# DXGK_SEGMENTDESCRIPTOR3 structure



## -description
<p>Contains information about a driver-supported segment that is composed of both BIOS-reserved memory (which is purged during a transition to a low-power state) and driver-reserved memory.</p>


## -syntax

````
typedef struct _DXGK_SEGMENTDESCRIPTOR3 {
  DXGK_SEGMENTFLAGS Flags;
  PHYSICAL_ADDRESS  BaseAddress;
  PHYSICAL_ADDRESS  CpuTranslatedAddress;
  SIZE_T            Size;
  UINT              NbOfBanks;
  SIZE_T            *pBankRangeTable;
  SIZE_T            CommitLimit;
  SIZE_T            SystemMemoryEndAddress;
  SIZE_T            Reserved;
} DXGK_SEGMENTDESCRIPTOR3;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>[out] A <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-segmentflags.md">DXGK_SEGMENTFLAGS</a> structure that identifies properties, in bit-field flags, for the segment.</p>
<p>Note that for an AGP-type aperture segment, the driver must exclusively set the <b>Agp</b> member of the structure in the union that DXGK_SEGMENTFLAGS contains. Although the AGP-type aperture segment is an aperture and is accessible to the CPU, if any other members are set, the adapter fails to initialize. </p>
</dd>

### -field <b>BaseAddress</b>

<dd>
<p>[out] The base address of the segment, as determined by the graphics processing unit (GPU). The physical address of an allocation that the video memory manager paged in the segment is assigned a GPU address that is offset from the base address that <b>BaseAddress</b> specifies.</p>
<p>The video memory manager ignores the base address of AGP-type aperture segments (where the <b>Agp</b> bit-field flag is specified in the <b>Flags</b> member) and instead uses the actual physical address of the segment within the AGP aperture, as determined on the bus where the GPU is located. In this situation, the driver can use addresses that the video memory manager generated for allocation directly without requiring translation.</p>
</dd>

### -field <b>CpuTranslatedAddress</b>

<dd>
<p>[out] The base address of the segment, relative to the bus that the GPU is connected on. For example, when the GPU is connected on the PCI bus, <b>CpuTranslatedAddress </b>is the base address of the usable range that is specified by a PCI base-address register (BAR). The driver specifies this address only if it specifies a CPU-accessible segment by setting the <b>CpuVisible</b> bit-field flag in the <b>Flags</b> member.</p>
<p>This member is ignored for aperture segments, including the AGP-type aperture segment.  The only exception occurs when the  user-mode display driver has not set up an alternate virtual address for a primary allocation (that is, when the driver has not set <b>UseAlternateVA</b> in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt--d3dddicb-lockflags.md">D3DDDICB_LOCKFLAGS</a> structure during a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-lockcb.md">pfnLockCb</a> function).</p>
<p>Before the video memory manager maps a virtual address to the physical range, the video memory manager translates this physical address based on the CPU view of the bus and informs the driver about the operation so the driver can set up an aperture to access the content of the segment at the specified location. </p>
</dd>

### -field <b>Size</b>

<dd>
<p>[out] The size, in bytes, of the segment. This size must be a multiple of the native host page size (for example, 4 KB on the x86 architecture).</p>
<p>For AGP-type aperture segments (where the <b>Agp</b> bit-field flag is specified in the <b>Flags</b> member), the video memory manager allocates as much aperture space as possible, so  this member is ignored.</p>
</dd>

### -field <b>NbOfBanks</b>

<dd>
<p>[out] The number of banks in the segment, if banking is used (that is, if the <b>UseBanking</b> bit-field flag is set in the <b>Flags</b> member).</p>
</dd>

### -field <b>pBankRangeTable</b>

<dd>
<p>[out] An array of values that indicates the ranges that delimit each bank in the segment. The array specifies the end addresses of the first bank through the <i>n</i>âˆ’1 bank (that is, the end offsets into the segment for each bank). Note the following: </p>
<ul>
<li>
<p>Banks are contiguous.</p>
</li>
<li>
<p>The first bank starts at offset zero of the segment.</p>
</li>
<li>
<p>The last bank ends at the end of the segment, so the driver is not required to specify the end address of the last bank.</p>
</li>
<li>
<p>The driver specifies this array only if it also sets the <b>UseBanking</b> bit-field flag in the <b>Flags</b> member.</p>
</li>
</ul>
</dd>

### -field <b>CommitLimit</b>

<dd>
<p>[out] The maximum number of bytes that can be committed to the segment. For a memory segment, the commit limit is always the same as the size of the segment, which is specified in the <b>Size</b> member. For an aperture segment, the driver can limit the amount of memory that can be committed to the segment on systems with small amounts of physical memory. </p>
</dd>

### -field <b>SystemMemoryEndAddress</b>

<dd>
<p>For segments that are partially composed of system memory, all allocations that begin after this address are purged in a transition to a hibernate state. Allocations that exist entirely in system memory, where the segment address is less than or equal to <b>SystemMemoryEndAddress</b>, are not evicted in this transition.</p>
<p>The display miniport driver should set this member to a non-<b>NULL</b> value if the segment is partially preserved in a transition to a hibernate state, in which case  the <b>PartiallyPreservedDuringHibernate</b> member in the <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-segmentflags.md">DXGK_SEGMENTFLAGS</a> structure should be set.</p>
<p>Driver-reserved memory runs from segment address 0 through <b>SystemMemoryEndAddress</b>, inclusive. BIOS-reserved memory runs from (<b>SystemMemoryEndAddress</b>+1) through the end of the segment.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by a WDDM 1.2 or later  display miniport drivers to return information about memory segments in response to a <a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a> function call in which the graphics subsystem specifies the <b>DXGKQAITYPE_QUERYSEGMENT3</b> value in the <b>Type</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure.</p>

<p>This structure is pointed to by the <b>pSegmentDescriptor</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddicb-lockflags.md">D3DDDICB_LOCKFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-segmentflags.md">DXGK_SEGMENTFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_SEGMENTDESCRIPTOR3 structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
