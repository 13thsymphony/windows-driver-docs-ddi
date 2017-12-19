---
UID: NE.ufs.UFS_FLAGS_DESCRIPTOR
title: UFS_FLAGS_DESCRIPTOR
author: windows-driver-content
description: UFS_FLAGS_DESCRIPTOR describes the different types of flags used by Universal Flash Storage (UFS) descriptors.
old-location: storage\ufs_flags_descriptor.htm
old-project: storage
ms.assetid: D530355F-5824-4F7C-84C4-57D3D03A7116
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: UFS_FLAGS_DESCRIPTOR, UFS_FLAGS_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFS_FLAGS_DESCRIPTOR
req.alt-loc: Ufs.h
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
req.product: Windows 10 or later.
---

# UFS_FLAGS_DESCRIPTOR enumeration



## -description
<b>UFS_FLAGS_DESCRIPTOR</b> describes the different types of flags used by Universal Flash Storage (UFS) descriptors.



## -syntax

````
typedef enum _UFS_FLAGS_DESCRIPTOR { 
  UFS_Reserved1                    = 0,
  UFS_fDeviceInit,
  UFS_fPermanentWPEn,
  UFS_fPowerOnWPEn,
  UFS_fBackgroundOpsEn,
  UFS_fDeviceLifeSpanModeEn,
  UFS_fPurgeEnable,
  UFS_Reserved2,
  UFS_fPhyResourceRemoval,
  UFS_fBusyRTC,
  UFS_Reserved3,
  UFS_fPermanentlyDisableFwUpdate,
  UFS_Reserved4,
  UFS_Reserved5
} UFS_FLAGS_DESCRIPTOR;
````


## -enum-fields

### -field UFS_Reserved1

Reserved for future use.


### -field UFS_fDeviceInit

Indicates the device initialization is in progress.


### -field UFS_fPermanentWPEn

Indicates permanent write protection is enabled.


### -field UFS_fPowerOnWPEn

Indicates power on write protection is enabled.


### -field UFS_fBackgroundOpsEn

Indicates the device is permitted to run
background operations.


### -field UFS_fDeviceLifeSpanModeEn

Indicates Device Life Span Mode is enabled.


### -field UFS_fPurgeEnable

Indicates Purge Operation is enabled.


### -field UFS_Reserved2

Reserved for future use.


### -field UFS_fPhyResourceRemoval

Indicates
that the dynamic capacity operation occurs on the device's EndPointReset or
a hardware reset. The host cannot reset this flag.


### -field UFS_fBusyRTC

Indicates the device is executing internal
operation related to Real Time Clock.


### -field UFS_Reserved3

Reserved for the Unified Memory Extension standard..


### -field UFS_fPermanentlyDisableFwUpdate

Indicates the UFS device will permanently
disallow future firmware updates to
the Universal Flash Storage (UFS) device.


### -field UFS_Reserved4

Reserved for the Unified Memory Extension standard.


### -field UFS_Reserved5

Reserved for the Unified Memory Extension standard.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufs.h</dt>
</dl>
</td>
</tr>
</table>