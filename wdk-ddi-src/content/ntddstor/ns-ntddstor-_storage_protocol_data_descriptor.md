---
UID: NS:ntddstor._STORAGE_PROTOCOL_DATA_DESCRIPTOR
title: "_STORAGE_PROTOCOL_DATA_DESCRIPTOR"
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return protocol-specific data from a storage device or adapter.
old-location: storage\storage_protocol_data_descriptor.htm
old-project: storage
ms.assetid: 292EE243-2952-4020-8EB0-C5127DF92318
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTORAGE_PROTOCOL_DATA_DESCRIPTOR, PSTORAGE_PROTOCOL_DATA_DESCRIPTOR, PSTORAGE_PROTOCOL_DATA_DESCRIPTOR structure pointer [Storage Devices], STORAGE_PROTOCOL_DATA_DESCRIPTOR, STORAGE_PROTOCOL_DATA_DESCRIPTOR structure [Storage Devices], _STORAGE_PROTOCOL_DATA_DESCRIPTOR, ntddstor/PSTORAGE_PROTOCOL_DATA_DESCRIPTOR, ntddstor/STORAGE_PROTOCOL_DATA_DESCRIPTOR, storage.storage_protocol_data_descriptor"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	STORAGE_PROTOCOL_DATA_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_PROTOCOL_DATA_DESCRIPTOR, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR
---

# _STORAGE_PROTOCOL_DATA_DESCRIPTOR structure
This structure is used in conjunction with <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to return protocol-specific data from a storage device or adapter. .

## Syntax
````
typedef struct _STORAGE_PROTOCOL_DATA_DESCRIPTOR {
  ULONG                          Version;
  ULONG                          Size;
  STORAGE_PROTOCOL_SPECIFIC_DATA ProtocolSpecificData;
} STORAGE_PROTOCOL_DATA_DESCRIPTOR, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR;
````

## Members


`Version`

The version of this structure.

`Size`

The total size of the descriptor, including the space for all protocol data.

`ProtocolSpecificData`

The protocol-specific data, of type <a href="..\ntddstor\ns-ntddstor-_storage_protocol_specific_data.md">STORAGE_PROTOCOL_SPECIFIC_DATA</a>.

## Remarks
When using <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve protocol-specific information in the <b>STORAGE_PROTOCOL_DATA_DESCRIPTOR</b>, configure the <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a> structure as follows:

<ul>
<li>
Allocate a buffer that can contains both a <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a> and a <a href="..\ntddstor\ns-ntddstor-_storage_protocol_specific_data.md">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure.

</li>
<li>
Set the <b>PropertyID</b>  field to <b>StorageAdapterProtocolSpecificProperty</b> or <b>StorageDeviceProtocolSpecificProperty</b> for a controller or device/namespace request, respectively.

</li>
<li>
Set the <b>QueryType</b>  field to <b>PropertyStandardQuery</b>.

</li>
<li>
Fill the <a href="..\ntddstor\ns-ntddstor-_storage_protocol_specific_data.md">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure with the desired values. The start of the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> is the <b>AdditionalParameters</b> field of <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>.

</li>
</ul>
To specify a type of NVMe protocol-specific information,  configure the <a href="..\ntddstor\ns-ntddstor-_storage_protocol_specific_data.md">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure as follows:

<ul>
<li>
Set the <b>ProtocolType</b>  field to <b>ProtocolTypeNVMe</b>.

</li>
<li>
Set the <b>DataType</b>  field to an enumeration value defined by <a href="..\ntddstor\ne-ntddstor-_storage_protocol_nvme_data_type.md">STORAGE_PROTOCOL_NVME_DATA_TYPE</a>:<ul>
<li>Use <b>NVMeDataTypeIdentify</b> to get Identify Controller data or Identify Namespace data.</li>
<li>Use <b>NVMeDataTypeLogPage</b> to get log pages (including SMART/health data).</li>
<li>Use <b>NVMeDataTypeFeature</b> to get features of the NVMe drive.</li>
</ul>


</li>
</ul>
To specify a type of ATA protocol-specific information,  configure the <a href="..\ntddstor\ns-ntddstor-_storage_protocol_specific_data.md">STORAGE_PROTOCOL_SPECIFIC_DATA</a> structure as follows:

<ul>
<li>
Set the <b>ProtocolType</b>  field to <b>ProtocolTypeAta</b>.

</li>
<li>
Set the <b>DataType</b>  field to an enumeration value defined by <a href="..\ntddstor\ne-ntddstor-_storage_protocol_ata_data_type.md">STORAGE_PROTOCOL_ATA_DATA_TYPE</a>:<ul>
<li>Use <b>AtaDataTypeIdentify</b> to identify the ATA drive.</li>
<li>Use <b>AtaDataTypeLogPage</b> to get log pages from the ATA drive.</li>
</ul>


</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ns-ntddstor-_storage_protocol_specific_data.md">STORAGE_PROTOCOL_SPECIFIC_DATA</a>



<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>