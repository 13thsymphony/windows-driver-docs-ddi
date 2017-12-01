---
UID: NS.ntddstor._DEVICE_DATA_SET_RANGE
title: DEVICE_DATA_SET_RANGE
author: windows-driver-content
description: The DEVICE_DATA_SET_RANGE structure specifies a block of data set ranges for the attributes for a device.
old-location: storage\device_data_set_range.htm
old-project: storage
ms.assetid: 9f610927-d8d0-44c5-8a66-0204953c1859
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DEVICE_DATA_SET_RANGE, DEVICE_DATA_SET_RANGE, *PDEVICE_DATA_SET_RANGE
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
req.alt-api: DEVICE_DATA_SET_RANGE
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

# DEVICE_DATA_SET_RANGE structure



## -description
<p>The <b>DEVICE_DATA_SET_RANGE</b> structure specifies a block of data set ranges for the attributes for a device. </p>
<p>The block of data set ranges is specified in the <a href="..\ntddstor\ns-ntddstor--device-manage-data-set-attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure that is contained in the system buffer of an <a href="..\ntddstor\ni-ntddstor-ioctl-storage-manage-data-set-attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.</p>


## -syntax

````
typedef struct _DEVICE_DATA_SET_RANGE {
  LONGLONG  StartingOffset;
  ULONGLONG LengthInBytes;
} DEVICE_DATA_SET_RANGE, *PDEVICE_DATA_SET_RANGE;
````


## -struct-fields
<dl>

### -field <b>StartingOffset</b>

<dd>
<p>Contains the starting offset, in bytes, of the data set range. The offset value must be block aligned.</p>
</dd>

### -field <b>LengthInBytes</b>

<dd>
<p>Contains the length, in bytes, of the data set range. The length value must be block aligned.</p>
</dd>
</dl>

## -remarks


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
<a href="..\ntddstor\ni-ntddstor-ioctl-storage-manage-data-set-attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_DATA_SET_RANGE structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
