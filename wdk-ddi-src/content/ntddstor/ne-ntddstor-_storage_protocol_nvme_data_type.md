---
UID: NE.ntddstor._STORAGE_PROTOCOL_NVME_DATA_TYPE
title: _STORAGE_PROTOCOL_NVME_DATA_TYPE
author: windows-driver-content
description: Describes the type of NVMe protocol-specific data that's to be queried during an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_protocol_nvme_data_type.htm
old-project: storage
ms.assetid: 02DB004B-F5B9-4CA2-9CA8-9C7BFB9BA5CD
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_PROTOCOL_NVME_DATA_TYPE, *PSTORAGE_PROTOCOL_NVME_DATA_TYPE, PSTORAGE_PROTOCOL_NVME_DATA_TYPE, STORAGE_PROTOCOL_NVME_DATA_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_PROTOCOL_NVME_DATA_TYPE
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

# _STORAGE_PROTOCOL_NVME_DATA_TYPE enumeration



## -description
Describes  the type of NVMe protocol-specific data that's to be queried during an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request.



## -syntax

````
typedef enum _STORAGE_PROTOCOL_NVME_DATA_TYPE { 
  NVMeDataTypeUnknown   = 0,
  NVMeDataTypeIdentify,
  NVMeDataTypeLogPage,
  NVMeDataTypeFeature
} STORAGE_PROTOCOL_NVME_DATA_TYPE, *PSTORAGE_PROTOCOL_NVME_DATA_TYPE;
````


## -enum-fields

### -field NVMeDataTypeUnknown

Unknown data type.


### -field NVMeDataTypeIdentify

Identify data type. This can be either Identify Controller data or Identify Namespace data. When this type of data is being queried, the ProtocolDataRequestValue field of <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> will have a value of <b>NVME_IDENTIFY_CNS_CONTROLLER</b> for adapter or <b>NVME_IDENTIFY_CNS_SPECIFIC_NAMESPACE</b> for namespace. If the ProtocolDataRequestValue is <b>NVME_IDENTIFY_CNS_SPECIFIC_NAMESPACE</b>, the ProtocolDataRequestSubValue field from the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> structure will have a value of the namespace ID.


### -field NVMeDataTypeLogPage

Log page data type.


### -field NVMeDataTypeFeature

Feature data type.


## -remarks
When using <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve protocol-specific information in the <a href="storage.storage_protocol_data_descriptor">STORAGE_PROTOCOL_DATA_DESCRIPTOR</a>, configure the <a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a> structure as follows:

Allocate a buffer that can contains both a <a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a> and a <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure.

Set the <b>PropertyID</b>  field to <b>StorageAdapterProtocolSpecificProperty</b> or <b>StorageDeviceProtocolSpecificProperty</b> for a controller or device/namespace request, respectively.

Set the <b>QueryType</b>  field to <b>PropertyStandardQuery</b>.

Fill the <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure with the desired values. The start of the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> is the <b>AdditionalParameters</b> field of <a href="storage.storage_property_query">STORAGE_PROPERTY_QUERY</a>.

To specify a type of NVMe protocol-specific information,  configure the <a href="storage.storage_protocol_specific_data">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure as follows:

Set the <b>ProtocolType</b>  field to <b>ProtocolTypeNVMe</b>.

Set the <b>DataType</b>  field to an enumeration value defined by <b>STORAGE_PROTOCOL_NVME_DATA_TYPE</b>:<ul>
<li>Use <b>NVMeDataTypeIdentify</b> to get Identify Controller data or Identify Namespace data.</li>
<li>Use <b>NVMeDataTypeLogPage</b> to get log pages (including SMART/health data).</li>
<li>Use <b>NVMeDataTypeFeature</b> to get features of the NVMe drive.</li>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_PROTOCOL_NVME_DATA_TYPE enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

