---
UID: NS.NTDDSTOR._STORAGE_PROPERTY_QUERY
title: _STORAGE_PROPERTY_QUERY
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to retrieve the properties of a storage device or adapter.
old-location: storage\storage_property_query.htm
old-project: storage
ms.assetid: 5f8e4fbd-706c-4694-bcba-927474a66e86
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_PROPERTY_QUERY, *PSTORAGE_PROPERTY_QUERY, STORAGE_PROPERTY_QUERY
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
req.alt-api: STORAGE_PROPERTY_QUERY
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

# _STORAGE_PROPERTY_QUERY structure



## -description
This structure is used in conjunction with <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve the properties of a storage device or adapter. 



## -syntax

````
typedef struct _STORAGE_PROPERTY_QUERY {
  STORAGE_PROPERTY_ID PropertyId;
  STORAGE_QUERY_TYPE  QueryType;
  UCHAR               AdditionalParameters[1];
} STORAGE_PROPERTY_QUERY, *PSTORAGE_PROPERTY_QUERY;
````


## -struct-fields

### -field PropertyId

Indicates whether the caller is requesting a device descriptor, an adapter descriptor, a write cache property, a device unique ID (DUID), or the device identifiers provided in the device's SCSI vital product data (VPD) page. For a list of the property IDs that can be assigned to this member, see <a href="storage.storage_property_id">STORAGE_PROPERTY_ID</a>. 


### -field QueryType

Contains flags indicating the type of query to be performed. For a list of the various query types that can be assigned to this member, see <a href="storage.storage_query_type">STORAGE_QUERY_TYPE</a>. 


### -field AdditionalParameters

Contains an array of bytes with additional input parameters that are needed for the <b>PropertyId</b> query. Not all <b>PropertyId</b> values require additional input parameters. 


## -remarks
The results of the query can be one of 
     several structures depending on the value of the <b>PropertyId</b> member. These values are enumerated by the 
     <a href="storage.storage_property_id">STORAGE_PROPERTY_ID</a> enumeration.

If the 
     <b>QueryType</b> member is set to 
     <b>PropertyExistsQuery</b>, then no structure is returned. For more info, see <a href="storage.storage_query_type">STORAGE_QUERY_TYPE</a>.


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
<a href="storage.storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>
</dt>
<dt>
<a href="storage.storage_query_type">STORAGE_QUERY_TYPE</a>
</dt>
<dt>
<a href="storage.storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.storage_adapter_descriptor">STORAGE_ADAPTER_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.storage_property_id">STORAGE_PROPERTY_ID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_PROPERTY_QUERY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

