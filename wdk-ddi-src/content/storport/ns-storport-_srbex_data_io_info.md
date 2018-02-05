---
UID : NS:storport._SRBEX_DATA_IO_INFO
title : "_SRBEX_DATA_IO_INFO"
author : windows-driver-content
description : The SRBEX_DATA_IO_INFO structure contains additional information related to a read or write request in an extended SRB.
old-location : storage\srbex_data_io_info.htm
old-project : storage
ms.assetid : D4B99D6F-0A0C-49CE-A8E2-19C1A835EDA6
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.srbex_data_io_info, SRBEX_DATA_IO_INFO structure [Storage Devices], storport/PSRBEX_DATA_IO_INFO, REQUEST_INFO_VALID_CACHEPRIORITY_FLAG, PSRBEX_DATA_IO_INFO structure pointer [Storage Devices], REQUEST_INFO_TEMPORARY_FLAG, storport/SRBEX_DATA_IO_INFO, PSRBEX_DATA_IO_INFO, REQUEST_INFO_HYBRID_WRITE_THROUGH_FLAG, REQUEST_INFO_SEQUENTIAL_IO_FLAG, REQUEST_INFO_WRITE_THROUGH_FLAG, REQUEST_INFO_NO_CACHE_FLAG, *PSRBEX_DATA_IO_INFO, REQUEST_INFO_PAGING_IO_FLAG, SRBEX_DATA_IO_INFO, _SRBEX_DATA_IO_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : storport.h
req.include-header : Storport.h, Srb.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SRBEX_DATA_IO_INFO, *PSRBEX_DATA_IO_INFO
req.product : Windows 10 or later.
---

# _SRBEX_DATA_IO_INFO structure
The <b>SRBEX_DATA_IO_INFO</b> structure contains additional information related to a read or write request in an extended SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SRBEX_DATA_IO_INFO {
  SRBEXDATATYPE Type;
  ULONG         Length;
  ULONG         Flags;
  ULONG         Key;
  ULONG         RWLength;
  BOOLEAN       IsWriteRequest;
  UCHAR         CachePriority;
  UCHAR         Reserved[2];
  ULONG         Reserved1[3];
} SRBEX_DATA_IO_INFO, *PSRBEX_DATA_IO_INFO;
````

## Members


`CachePriority`

Priority level for a hybrid cache read or write.

This member is valid starting with Windows 8.1 Update.

`Flags`

Flags set for handling the request. May be a combination of these values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_NO_CACHE_FLAG"></a><a id="request_info_no_cache_flag"></a><dl>
<dt><b>REQUEST_INFO_NO_CACHE_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Non-cached writes are specified for this request.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_PAGING_IO_FLAG"></a><a id="request_info_paging_io_flag"></a><dl>
<dt><b>REQUEST_INFO_PAGING_IO_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Paging IO is specified for this request.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_SEQUENTIAL_IO_FLAG"></a><a id="request_info_sequential_io_flag"></a><dl>
<dt><b>REQUEST_INFO_SEQUENTIAL_IO_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Reads or writes are sequential.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_TEMPORARY_FLAG"></a><a id="request_info_temporary_flag"></a><dl>
<dt><b>REQUEST_INFO_TEMPORARY_FLAG</b></dt>
</dl>
</td>
<td width="60%">
The file for this request is temporary.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_WRITE_THROUGH_FLAG"></a><a id="request_info_write_through_flag"></a><dl>
<dt><b>REQUEST_INFO_WRITE_THROUGH_FLAG</b></dt>
</dl>
</td>
<td width="60%">
No system buffering for the request.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_HYBRID_WRITE_THROUGH_FLAG"></a><a id="request_info_hybrid_write_through_flag"></a><dl>
<dt><b>REQUEST_INFO_HYBRID_WRITE_THROUGH_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Perform a hybrid cache write through to disk

This flag is available starting with Windows 8.1 Update.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_VALID_CACHEPRIORITY_FLAG"></a><a id="request_info_valid_cachepriority_flag"></a><dl>
<dt><b>REQUEST_INFO_VALID_CACHEPRIORITY_FLAG</b></dt>
</dl>
</td>
<td width="60%">
The hybrid cache priority level is valid for this I/O.

This flag is available starting with Windows 8.1 Update.

</td>
</tr>
</table>

`IsWriteRequest`

TRUE if the I/O operation in the SRB is a write request. Otherwise, FALSE; the I/O operation is a read request.

`Key`

A tag value to identify a block of data transferred.

`Length`

Length of the data in this structure, in bytes, starting with the <b>Flags</b> member. Set to SRBEX_DATA_IO_INFO_LENGTH.

`Reserved`

This member is reserved. Set to 0.

`Reserved1`

This member is reserved. Set to 0.

This member is present starting with Windows 8.1 Update.

`RWLength`

The length, in bytes of the data to transfer.

`Type`

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeIoInfo</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | storport.h (include Storport.h, Srb.h) |

## See Also

<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA_IO_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>