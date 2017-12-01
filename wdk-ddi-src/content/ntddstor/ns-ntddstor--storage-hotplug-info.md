---
UID: NS.ntddstor._STORAGE_HOTPLUG_INFO
title: STORAGE_HOTPLUG_INFO
author: windows-driver-content
description: The STORAGE_HOTPLUG_INFO structure provides hotplug information for a device.
old-location: storage\storage_hotplug_info.htm
old-project: storage
ms.assetid: dcfd5a42-cb76-4386-9f8f-98e0a217c49a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_HOTPLUG_INFO, STORAGE_HOTPLUG_INFO, *PSTORAGE_HOTPLUG_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_HOTPLUG_INFO
req.alt-loc: ntddstor.h
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
req.iface: 
---

# STORAGE_HOTPLUG_INFO structure



## -description
<p>The STORAGE_HOTPLUG_INFO structure provides hotplug information for a device. </p>


## -syntax

````
typedef struct _STORAGE_HOTPLUG_INFO {
  ULONG   Size;
  BOOLEAN MediaRemovable;
  BOOLEAN MediaHotplug;
  BOOLEAN DeviceHotplug;
  BOOLEAN WriteCacheEnableOverride;
} STORAGE_HOTPLUG_INFO, *PSTORAGE_HOTPLUG_INFO;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>Indicates the size, in bytes, of this structure.</p>
</dd>

### -field <b>MediaRemovable</b>

<dd>
<p>Specifies whether the media is removable. If set to a nonzero value, the device media is removable. If set to zero, the device media is not removable. </p>
</dd>

### -field <b>MediaHotplug</b>

<dd>
<p>Specifies whether the media is lockable. If set to a nonzero value, the device media is not lockable. If set to zero, the device media is lockable.</p>
</dd>

### -field <b>DeviceHotplug</b>

<dd>
<p>Specifies whether the device is a hotplug device. If set to a nonzero value, the device is a hotplug device. If set to zero, the device is not a hotplug device.</p>
</dd>

### -field <b>WriteCacheEnableOverride</b>

<dd>
<p>Do not use; set the value to <b>NULL</b>.</p>
</dd>
</dl>

## -remarks
<p>The value of the <b>Size</b> member also identifies the version of this structure. New members will be added to this structure in the future. If the value of the <b>Size</b> member is <b>sizeof</b>(STORAGE_HOTPLUG_INFO), the current version of the structure is the same as the version you compiled with. If the value is not <b>sizeof</b>(STORAGE_HOTPLUG_INFO), the current version contains additional members.</p>

<p>Microsoft Windows XP includes support for hotplug devices. A hotplug device refers to a device whose <b>RemovalPolicy</b> value displayed in the Device Manager is <b>ExpectSurpriseRemoval</b>. To query whether a particular device is a hotplug device, use the <a href="..\ntddstor\ni-ntddstor-ioctl-storage-get-hotplug-info.md">IOCTL_STORAGE_GET_HOTPLUG_INFO</a> request. To set the hotplug properties of a device, use the <a href="..\ntddstor\ni-ntddstor-ioctl-storage-set-hotplug-info.md">IOCTL_STORAGE_SET_HOTPLUG_INFO</a> request.</p>

<p>In the case of the IOCTL_STORAGE_SET_HOTPLUG_INFO request, the <b>DeviceHotplug</b> member of the STORAGE_HOTPLUG_INFO structure determines what action is taken. If the value of that member is nonzero, the value for the device's removal policy in the registry is set to <b>ExpectSurpriseRemoval</b> and all levels of caching are disabled. If the value of <b>DeviceHotplug</b> is zero, the removal policy is set to <b>ExpectOrderlyRemoval</b>, and caching may be selectively enabled. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl-storage-get-hotplug-info.md">IOCTL_STORAGE_GET_HOTPLUG_INFO</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl-storage-set-hotplug-info.md">IOCTL_STORAGE_SET_HOTPLUG_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_HOTPLUG_INFO structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
