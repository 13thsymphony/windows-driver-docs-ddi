---
UID: NS:ntddstor._STORAGE_PROTOCOL_SPECIFIC_DATA
title: "_STORAGE_PROTOCOL_SPECIFIC_DATA"
author: windows-driver-content
description: Describes protocol-specific device data, provided in the input and output buffer of an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_protocol_specific_data.htm
old-project: storage
ms.assetid: 74569A0A-5828-4533-8974-4DE0B4EAAAEB
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_PROTOCOL_SPECIFIC_DATA, PSTORAGE_PROTOCOL_SPECIFIC_DATA, PSTORAGE_PROTOCOL_SPECIFIC_DATA structure pointer [Storage Devices], STORAGE_PROTOCOL_SPECIFIC_DATA, STORAGE_PROTOCOL_SPECIFIC_DATA structure [Storage Devices], _STORAGE_PROTOCOL_SPECIFIC_DATA, ntddstor/PSTORAGE_PROTOCOL_SPECIFIC_DATA, ntddstor/STORAGE_PROTOCOL_SPECIFIC_DATA, storage.storage_protocol_specific_data"
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
-	STORAGE_PROTOCOL_SPECIFIC_DATA
product: Windows
targetos: Windows
req.typenames: STORAGE_PROTOCOL_SPECIFIC_DATA, *PSTORAGE_PROTOCOL_SPECIFIC_DATA
---

# _STORAGE_PROTOCOL_SPECIFIC_DATA structure
Describes  protocol-specific device data, provided in the input and output buffer of an  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request.

## Syntax
```
typedef struct _STORAGE_PROTOCOL_SPECIFIC_DATA {
  STORAGE_PROTOCOL_TYPE ProtocolType;
  ULONG                 DataType;
  ULONG                 ProtocolDataRequestValue;
  ULONG                 ProtocolDataRequestSubValue;
  ULONG                 ProtocolDataOffset;
  ULONG                 ProtocolDataLength;
  ULONG                 FixedProtocolReturnData;
  ULONG                 Reserved[3];
} *PSTORAGE_PROTOCOL_SPECIFIC_DATA, STORAGE_PROTOCOL_SPECIFIC_DATA;
```

## Members


`ProtocolType`

The protocol type. Values for this member are defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931818">STORAGE_PROTOCOL_TYPE</a> enumeration.

`DataType`

The protocol data type. Data types are defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931816">STORAGE_PROTOCOL_NVME_DATA_TYPE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn931813">STORAGE_PROTOCOL_ATA_DATA_TYPE</a> enumerations.

`ProtocolDataRequestValue`

The protocol data request value.

`ProtocolDataRequestSubValue`

The sub value of the protocol data request.

`ProtocolDataOffset`

The offset of the data buffer that is from the beginning of this structure. The typical value can be sizeof(<b>STORAGE_PROTOCOL_SPECIFIC_DATA</b>).

`ProtocolDataLength`

The length of the protocol data.

`FixedProtocolReturnData`

The returned data.

`Reserved`

Reserved for future use.

## Remarks
When using <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve protocol-specific information in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931815">STORAGE_PROTOCOL_DATA_DESCRIPTOR</a>, configure the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a> structure as follows:

<ul>
<li>
Allocate a buffer that can contains both a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a> and a <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> structure.

</li>
<li>
Set the <b>PropertyID</b>  field to <b>StorageAdapterProtocolSpecificProperty</b> or <b>StorageDeviceProtocolSpecificProperty</b> for a controller or device/namespace request, respectively.

</li>
<li>
Set the <b>QueryType</b>  field to <b>PropertyStandardQuery</b>.

</li>
<li>
Fill the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> structure with the desired values. The start of the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> is the <b>AdditionalParameters</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a>.

</li>
</ul>
To specify a type of NVMe protocol-specific information,  configure the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> structure as follows:

<ul>
<li>
Set the <b>ProtocolType</b>  field to <b>ProtocolTypeNVMe</b>.

</li>
<li>
Set the <b>DataType</b>  field to an enumeration value defined by <a href="https://msdn.microsoft.com/library/windows/hardware/dn931816">STORAGE_PROTOCOL_NVME_DATA_TYPE</a>:<ul>
<li>Use <b>NVMeDataTypeIdentify</b> to get Identify Controller data or Identify Namespace data.</li>
<li>Use <b>NVMeDataTypeLogPage</b> to get log pages (including SMART/health data).</li>
<li>Use <b>NVMeDataTypeFeature</b> to get features of the NVMe drive.</li>
</ul>


</li>
</ul>
To specify a type of ATA protocol-specific information,  configure the <b>STORAGE_PROTOCOL_SPECIFIC_DATA</b> structure as follows:

<ul>
<li>
Set the <b>ProtocolType</b>  field to <b>ProtocolTypeAta</b>.

</li>
<li>
Set the <b>DataType</b>  field to an enumeration value defined by <a href="https://msdn.microsoft.com/library/windows/hardware/dn931813">STORAGE_PROTOCOL_ATA_DATA_TYPE</a>:<ul>
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931817">STORAGE_PROTOCOL_SPECIFIC_DATA</a>