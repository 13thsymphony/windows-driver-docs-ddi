---
UID: NS.NTDDSTOR._STORAGE_PROTOCOL_DATA_DESCRIPTOR
title: _STORAGE_PROTOCOL_DATA_DESCRIPTOR
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return protocol-specific data from a storage device or adapter.
old-location: storage\storage_protocol_data_descriptor.htm
old-project: storage
ms.assetid: 292EE243-2952-4020-8EB0-C5127DF92318
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_PROTOCOL_DATA_DESCRIPTOR, STORAGE_PROTOCOL_DATA_DESCRIPTOR, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR
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
req.alt-api: STORAGE_PROTOCOL_DATA_DESCRIPTOR
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

# _STORAGE_PROTOCOL_DATA_DESCRIPTOR structure



## -description
This structure is used in conjunction with <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to return protocol-specific data from a storage device or adapter. .



## -syntax

````
typedef struct _STORAGE_PROTOCOL_DATA_DESCRIPTOR {
  ULONG                          Version;
  ULONG                          Size;
  STORAGE_PROTOCOL_SPECIFIC_DATA ProtocolSpecificData;
} STORAGE_PROTOCOL_DATA_DESCRIPTOR, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR;
````


## -struct-fields

### -field Version

The version of this structure.


### -field Size

The total size of the descriptor, including the space for all protocol data.


### -field ProtocolSpecificData

The protocol-specific data, of type <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a>.


## -remarks
When using <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve protocol-specific information in the <b>STORAGE_PROTOCOL_DATA_DESCRIPTOR</b>, configure the <a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a> structure as follows:

Allocate a buffer that can contains both a <a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a> and a <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure.

Set the <b>PropertyID</b>  field to <b>StorageAdapterProtocolSpecificProperty</b> or <b>StorageDeviceProtocolSpecificProperty</b> for a controller or device/namespace request, respectively.

Set the <b>QueryType</b>  field to <b>PropertyStandardQuery</b>.

Fill the <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure with the desired values. The start of the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> is the <b>AdditionalParameters</b> field of <a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a>.

To specify a type of NVMe protocol-specific information,  configure the <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure as follows:

Set the <b>ProtocolType</b>  field to <b>ProtocolTypeNVMe</b>.

Set the <b>DataType</b>  field to an enumeration value defined by <a href="storage.storage_protocol_nvme_data_type">STORAGE_PROTOCOL_NVME_DATA_TYPE</a>:<ul>
<li>Use <b>NVMeDataTypeIdentify</b> to get Identify Controller data or Identify Namespace data.</li>
<li>Use <b>NVMeDataTypeLogPage</b> to get log pages (including SMART/health data).</li>
<li>Use <b>NVMeDataTypeFeature</b> to get features of the NVMe drive.</li>
</ul>


To specify a type of ATA protocol-specific information,  configure the <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure as follows:

Set the <b>ProtocolType</b>  field to <b>ProtocolTypeAta</b>.

Set the <b>DataType</b>  field to an enumeration value defined by <a href="storage.storage_protocol_ata_data_type">STORAGE_PROTOCOL_ATA_DATA_TYPE</a>:<ul>
<li>Use <b>AtaDataTypeIdentify</b> to identify the ATA drive.</li>
<li>Use <b>AtaDataTypeLogPage</b> to get log pages from the ATA drive.</li>
</ul>



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
<a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_PROTOCOL_DATA_DESCRIPTOR structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

