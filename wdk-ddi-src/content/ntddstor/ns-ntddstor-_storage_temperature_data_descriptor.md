---
UID: NS.NTDDSTOR._STORAGE_TEMPERATURE_DATA_DESCRIPTOR
title: _STORAGE_TEMPERATURE_DATA_DESCRIPTOR
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return temperature data from a storage device or adapter.
old-location: storage\storage_temperature_data_descriptor.htm
old-project: storage
ms.assetid: A6041B10-0296-4A96-B65C-C35B8DCB2B5D
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_TEMPERATURE_DATA_DESCRIPTOR, PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, *PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, STORAGE_TEMPERATURE_DATA_DESCRIPTOR
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
req.alt-api: STORAGE_TEMPERATURE_DATA_DESCRIPTOR
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

# _STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure



## -description
This structure is used in conjunction with <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to return temperature data from a storage device or adapter. 



## -syntax

````
typedef struct _STORAGE_TEMPERATURE_DATA_DESCRIPTOR {
  ULONG                    Version;
  ULONG                    Size;
  SHORT                    CriticalTemperature;
  SHORT                    WarningTemperature;
  USHORT                   InfoCount;
  UCHAR                    Reserved0[2];
  ULONG                    Reserved1[2];
  STORAGE_TEMPERATURE_INFO TemperatureInfo[ANYSIZE_ARRAY];
} STORAGE_TEMPERATURE_DATA_DESCRIPTOR, *PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR;
````


## -struct-fields

### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to the structure.


### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this structure.


### -field CriticalTemperature

Indicates the minimum temperature in degrees Celsius that may prevent normal operation. Exceeding this temperature may result in possible data loss, automatic device shutdown, extreme performance throttling, or permanent damage.      


### -field WarningTemperature

Indicates the maximum temperature in degrees Celsius at which the device is capable of operating continuously without degrading operation or reliability.    


### -field InfoCount

Specifies the number of <a href="storage.storage_temperature_info">STORAGE_TEMPERATURE_INFO</a> structures reported in <b>TemperatureInfo</b>. More than one set of temperature data may be returned when there are multiple sensors in the drive.


### -field Reserved0

Reserved for future use.


### -field Reserved1

Reserved for future use.


### -field TemperatureInfo[ANYSIZE_ARRAY]

Device temperature data, of type <a href="storage.storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

