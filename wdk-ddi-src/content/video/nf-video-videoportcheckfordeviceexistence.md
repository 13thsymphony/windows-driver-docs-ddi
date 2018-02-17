---
UID: NF:video.VideoPortCheckForDeviceExistence
title: VideoPortCheckForDeviceExistence function
author: windows-driver-content
description: The VideoPortCheckForDeviceExistence function determines whether the specified PCI device exists in the system.
old-location: display\videoportcheckfordeviceexistence.htm
old-project: display
ms.assetid: 2e0480a5-39d3-4977-9c0f-508bcf6c29a8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoportcheckfordeviceexistence, VideoPortCheckForDeviceExistence, VideoPort_Functions_3cb7198b-a2fe-423c-b0f3-11a154d087af.xml, video/VideoPortCheckForDeviceExistence, VideoPortCheckForDeviceExistence function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortCheckForDeviceExistence
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortCheckForDeviceExistence function
The <b>VideoPortCheckForDeviceExistence</b> function determines whether the specified PCI device exists in the system.

## Syntax

````
BOOLEAN VideoPortCheckForDeviceExistence(
  _In_ PVOID  HwDeviceExtension,
  _In_ USHORT VendorId,
  _In_ USHORT DeviceId,
  _In_ UCHAR  RevisionId,
  _In_ USHORT SubVendorId,
  _In_ USHORT SubSystemId,
  _In_ ULONG  Flags
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`VendorId`

Specifies the vendor ID.

`DeviceId`

Specifies the device ID.

`RevisionId`

Specifies the revision ID.

`SubVendorId`

Specifies the subvendor ID.

`SubSystemId`

Specifies the subsystem ID.

`Flags`

Is a set of flags that determine whether the <i>RevisionID</i> and <i>SubSystemID</i> parameters should be used in checking for the new device. This parameter can be the logical OR of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CDE_USE_REVISION

</td>
<td>
Use the value in the <i>RevisionID</i> parameter in checking for the new device.

</td>
</tr>
<tr>
<td>
CDE_USE_SUBSYSTEM_IDS

</td>
<td>
Use the value in the <i>SubSystemID</i> parameter in checking for the new device.

</td>
</tr>
</table>


## Return Value

<b>VideoPortCheckForDeviceExistence</b> returns <b>TRUE</b> if the device exists in the system, and <b>FALSE</b> otherwise.

## Remarks

For more information about PCI identifiers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |