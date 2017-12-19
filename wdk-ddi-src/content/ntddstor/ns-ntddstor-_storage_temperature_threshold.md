---
UID: NS.NTDDSTOR._STORAGE_TEMPERATURE_THRESHOLD
title: _STORAGE_TEMPERATURE_THRESHOLD
author: windows-driver-content
description: This structure is used to set the over or under temperature threshold of a storage device (via IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD).
old-location: storage\storage_temperature_threshold.htm
old-project: storage
ms.assetid: 19096AD2-5149-4AE1-94CD-9004ED8C24DC
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_TEMPERATURE_THRESHOLD, STORAGE_TEMPERATURE_THRESHOLD, *PSTORAGE_TEMPERATURE_THRESHOLD, PSTORAGE_TEMPERATURE_THRESHOLD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_TEMPERATURE_THRESHOLD
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
---

# _STORAGE_TEMPERATURE_THRESHOLD structure



## -description
This structure is used to set the over or under temperature threshold of a storage device (via <a href="..\ntddstor\ni-ntddstor-ioctl_storage_set_temperature_threshold.md">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>).



## -syntax

````
typedef struct _STORAGE_TEMPERATURE_THRESHOLD {
  ULONG   Version;
  ULONG   Size;
  USHORT  Flags;
  USHORT  Index;
  SHORT   Threshold;
  BOOLEAN OverThreshold;
  UCHAR   Reserved;
} STORAGE_TEMPERATURE_THRESHOLD, *PSTORAGE_TEMPERATURE_THRESHOLD;
````


## -struct-fields

### -field Version

The version of the structure.


### -field Size

The size of this structure. This should be set to sizeof(<b>STORAGE_TEMPERATURE_THRESHOLD</b>).


### -field Flags

Flags set for this request. The following are valid flags.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_COMMAND_FLAG_ADAPTER_REQUEST</b></td>
<td>This flag indicates the request to target an adapter instead of device.</td>
</tr>
</table>
 


### -field Index

Identifies the instance of temperature information. Starts from 0. Index 0 may indicate a composite value.


### -field Threshold

A signed value that indicates the temperature of the threshold, in degrees Celsius.


### -field OverThreshold

Indicates if the <i>Threshold</i> specifies the over or under temperature threshold. If <b>true</b>, set the <b>OverThreshold</b> temperature value of the device; otherwise, set the <b>UnderThreshold</b> temperature value. 


### -field Reserved

Reserved for future use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Server

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
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
<dt>
<a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a>
</dt>
<dt>
<a href="storage.storage_property_id">STORAGE_PROPERTY_ID</a>
</dt>
<dt>
<a href="storage.storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_TEMPERATURE_THRESHOLD structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

