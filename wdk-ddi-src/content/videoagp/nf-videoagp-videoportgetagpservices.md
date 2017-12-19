---
UID: NF.videoagp.VideoPortGetAgpServices
title: VideoPortGetAgpServices function
author: windows-driver-content
description: The VideoPortGetAgpServices function is obsolete and is supported only for backward compatibility with existing drivers.
old-location: display\videoportgetagpservices.htm
old-project: display
ms.assetid: 3b01831d-d429-4dc5-9b12-a0e1fc58634d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: VideoPortGetAgpServices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortGetAgpServices
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# VideoPortGetAgpServices function



## -description
The <b>VideoPortGetAgpServices</b> function is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="display.videoportqueryservices">VideoPortQueryServices</a>.

<b>VideoPortGetAgpServices</b> returns a list of video port driver-implemented AGP service functions.



## -syntax

````
BOOLEAN VideoPortGetAgpServices(
  _In_ PVOID                    HwDeviceExtension,
  _In_ PVIDEO_PORT_AGP_SERVICES AgpServices
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param AgpServices [in]

Pointer to an uninitialized, miniport driver-allocated <a href="display.video_port_agp_services">VIDEO_PORT_AGP_SERVICES</a> structure.


## -returns
<b>VideoPortGetAgpServices</b> returns <b>TRUE</b> after it successfully initializes the VIDEO_PORT_AGP_SERVICES structure to which <i>AgpServices</i> points; otherwise it returns <b>FALSE</b>.


## -remarks
PnP video miniport drivers that can use AGP should call <b>VideoPortGetAgpServices</b>.

The video port driver initializes the <a href="display.video_port_agp_services">VIDEO_PORT_AGP_SERVICES</a> structure as follows:

All function pointers are initialized to point to the corresponding video port driver-implemented AGP service functions.

The <b>AllocationLimit</b> field is initialized to the maximum amount of AGP memory that a miniport driver is allowed to commit, in bytes.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Videoagp.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.videoportqueryservices">VideoPortQueryServices</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_free_physical.md">AgpFreePhysical</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_free_virtual.md">AgpFreeVirtual</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_release_physical.md">AgpReleasePhysical</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_release_virtual.md">AgpReleaseVirtual</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>
</dt>
<dt><b>AgpReleasePhysical</b></dt>
<dt>
<a href="display.video_port_agp_services">VIDEO_PORT_AGP_SERVICES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetAgpServices function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

