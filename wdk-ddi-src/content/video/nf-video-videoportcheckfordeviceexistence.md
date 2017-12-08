---
UID: NF.video.VideoPortCheckForDeviceExistence
title: VideoPortCheckForDeviceExistence function
author: windows-driver-content
description: The VideoPortCheckForDeviceExistence function determines whether the specified PCI device exists in the system.
old-location: display\videoportcheckfordeviceexistence.htm
old-project: display
ms.assetid: 2e0480a5-39d3-4977-9c0f-508bcf6c29a8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortCheckForDeviceExistence
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
req.alt-api: VideoPortCheckForDeviceExistence
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

# VideoPortCheckForDeviceExistence function



## -description
The <b>VideoPortCheckForDeviceExistence</b> function determines whether the specified PCI device exists in the system.


## -syntax

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


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param VendorId [in]

Specifies the vendor ID.

### -param DeviceId [in]

Specifies the device ID.

### -param RevisionId [in]

Specifies the revision ID.

### -param SubVendorId [in]

Specifies the subvendor ID.

### -param SubSystemId [in]

Specifies the subsystem ID.

### -param Flags [in]

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
 

## -returns
<b>VideoPortCheckForDeviceExistence</b> returns <b>TRUE</b> if the device exists in the system, and <b>FALSE</b> otherwise.

## -remarks
For more information about PCI identifiers, see <a href="devinst.identifiers_for_pci_devices">Identifiers for PCI Devices</a>. 

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
Available in Windows XP and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
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