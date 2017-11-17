---
UID: NC.videoagp.PAGP_FREE_PHYSICAL
title: PAGP_FREE_PHYSICAL
author: windows-driver-content
description: The AgpFreePhysical function frees system memory that was committed by a previous call to AgpCommitPhysical.
old-location: display\agpfreephysical.htm
ms.assetid: bb0e3330-5601-47dd-afc6-94a70b42daaf
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AgpFreePhysical
req.alt-loc: videoagp.h
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
ms.keywords: VPOSVERSIONINFO, VPOSVERSIONINFO, *PVPOSVERSIONINFO
req.iface: 
req.product: Windows 10 or later.
---

# PAGP_FREE_PHYSICAL callback



## -description
<p>The <b>AgpFreePhysical</b> function frees system memory that was committed by a previous call to <a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>.</p>


## -prototype

````
PAGP_FREE_PHYSICAL AgpFreePhysical;

VOID APIENTRY AgpFreePhysical(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID PhysicalReserveContext,
  _In_ ULONG Pages,
  _In_ ULONG Offset
)
{ ... }
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the device extension of the miniport driver.</p>
</dd>

### -param <i>PhysicalReserveContext</i> [in]

<dd>
<p>Identifies a reserved physical address range. This context handle was obtained from <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>.</p>
</dd>

### -param <i>Pages</i> [in]

<dd>
<p>Specifies the number of pages of system memory that the video port driver should unmap.</p>
</dd>

### -param <i>Offset</i> [in]

<dd>
<p>Specifies the page offset into the reserved physical address range identified by <b>PhysicalReserveContext</b> that indicates the actual base address at which to unmap system memory.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>When a miniport driver calls <b>AgpFreePhysical</b>, <b>Pages</b> pages of physical memory are unlocked and unmapped from the AGP-decodable physical address range. This range begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The miniport driver must specify that the exact offset and number of pages be freed as were committed in a prior call to <a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>.</p>

<p>When a miniport driver calls <b>AgpFreePhysical</b>, <b>Pages</b> pages of physical memory are unlocked and unmapped from the AGP-decodable physical address range. This range begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The miniport driver must specify that the exact offset and number of pages be freed as were committed in a prior call to <a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Videoagp.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4da0f5cb-a017-4df5-958b-c76b7a08495a">AgpReleasePhysical</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_FREE_PHYSICAL callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
