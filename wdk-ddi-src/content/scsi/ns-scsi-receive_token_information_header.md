---
UID : NS:scsi.RECEIVE_TOKEN_INFORMATION_HEADER
title : RECEIVE_TOKEN_INFORMATION_HEADER
author : windows-driver-content
description : The RECEIVE_TOKEN_INFORMATION_HEADER structure contains information returned as status from an offload data transfer operation.
old-location : storage\receive_token_information_header.htm
old-project : storage
ms.assetid : 3D8BF059-2063-499E-B287-41EE184A2264
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : SERVICE_ACTION_POPULATE_TOKEN, scsi/PRECEIVE_TOKEN_INFORMATION_HEADER, PRECEIVE_TOKEN_INFORMATION_HEADER structure pointer [Storage Devices], TRANSFER_COUNT_UNITS_GIBIBYTES, PRECEIVE_TOKEN_INFORMATION_HEADER, TRANSFER_COUNT_UNITS_EXBIBYTES, TRANSFER_COUNT_UNITS_BYTES, TRANSFER_COUNT_UNITS_NUMBER_BLOCKS, TRANSFER_COUNT_UNITS_MEBIBYTES, scsi/RECEIVE_TOKEN_INFORMATION_HEADER, storage.receive_token_information_header, TRANSFER_COUNT_UNITS_KIBIBYTES, TRANSFER_COUNT_UNITS_PEBIBYTES, TRANSFER_COUNT_UNITS_TEBIBYTES, RECEIVE_TOKEN_INFORMATION_HEADER structure [Storage Devices], RECEIVE_TOKEN_INFORMATION_HEADER, SERVICE_ACTION_WRITE_USING_TOKEN, *PRECEIVE_TOKEN_INFORMATION_HEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : scsi.h
req.include-header : Scsi.h
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
req.typenames : RECEIVE_TOKEN_INFORMATION_HEADER, *PRECEIVE_TOKEN_INFORMATION_HEADER
req.product : Windows 10 or later.
---

# RECEIVE_TOKEN_INFORMATION_HEADER structure
The <b>RECEIVE_TOKEN_INFORMATION_HEADER</b> structure contains information returned as status from an offload data transfer operation.

## Syntax
````
typedef struct _RECEIVE_TOKEN_INFORMATION_HEADER {
  UCHAR AvailableData[4];
  UCHAR ResponseToServiceAction  :5;
  UCHAR Reserved1  :3;
  UCHAR OperationStatus  :7;
  UCHAR Reserved2   :1;
  UCHAR OperationCounter[2];
  UCHAR EstimatedStatusUpdateDelay[4];
  UCHAR CompletionStatus;
  UCHAR SenseDataFieldLength;
  UCHAR SenseDataLength;
  UCHAR TransferCountUnits;
  UCHAR TransferCount[8];
  UCHAR SegmentsProcessed[2];
  UCHAR Reserved3[6];
  UCHAR SenseData[ANYSIZE_ARRAY];
} RECEIVE_TOKEN_INFORMATION_HEADER, *PRECEIVE_TOKEN_INFORMATION_HEADER;
````

## Members


`AvailableData`

The amount of data available in the <b>SenseData</b> array and any additional result information.

`CompletionStatus`

SCSI status code for the copy command operation.

`EstimatedStatusUpdateDelay`

The recommended time, in milliseconds, to wait before sending the next RECEIVE COPY STATUS command for updated information about the current copy operation.

`OperationCounter`

The number of commands processed for the current copy operation.

`OperationStatus`

The current status of the copy operation. The status can be one of the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
The operation completed unsuccessfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
The operation completed successfully but the copy initiator should verify that all data was transferred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x10</dt>
</dl>
</td>
<td width="60%">
The operation is in progress. Foreground or background operation state is unknown.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x11</dt>
</dl>
</td>
<td width="60%">
The operation is in progress in the foreground.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x12</dt>
</dl>
</td>
<td width="60%">
The operation is in progress in the background.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x60</dt>
</dl>
</td>
<td width="60%">
The operation was terminated. Possibly by an existing resource reservation.

</td>
</tr>
</table>

`Reserved1`

Reserved.

`Reserved2`

Reserved.

`Reserved3`

Reserved.

`ResponseToServiceAction`

A response code indicating which command action the response is for. The service action codes are the following.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SERVICE_ACTION_POPULATE_TOKEN"></a><a id="service_action_populate_token"></a><dl>
<dt><b>SERVICE_ACTION_POPULATE_TOKEN</b></dt>
</dl>
</td>
<td width="60%">
The response information is for a POPULATE TOKEN command.

</td>
</tr>
<tr>
<td width="40%"><a id="SERVICE_ACTION_WRITE_USING_TOKEN"></a><a id="service_action_write_using_token"></a><dl>
<dt><b>SERVICE_ACTION_WRITE_USING_TOKEN</b></dt>
</dl>
</td>
<td width="60%">
The response information is for a WRITE USING TOKEN command.

</td>
</tr>
</table>

`SegmentsProcessed`

The number of segments processed for the data transfer operation. Segments are copy length units used internally by a storage device's copy provider. On Windowssystems, this value is reserved and applications must ignore this member.

`SenseData`

Sense data returned for the copy operation.

`SenseDataFieldLength`

The length, in bytes, of the entire data area available for sense data. This value is always &gt;=  <b>SenseDataLength</b>.

`SenseDataLength`

The length, in bytes, of the data in <b>SenseData</b>.

`TransferCount`

The length of data transferred in the operation. The unit type in <b>TransferCountUnits</b> is applied to this value to give the total byte count.

`TransferCountUnits`

The byte units applied to <i>TransferCount</i>. Each unit expansion is a exponent in base 2. The multiplier value of <b>TRANSFER_COUNT_UNITS_KIBIBYTES</b>, for example, is 1024 and not 1000. The defined units are the following.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_BYTES"></a><a id="transfer_count_units_bytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_BYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in bytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_KIBIBYTES"></a><a id="transfer_count_units_kibibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_KIBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in kilobytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_MEBIBYTES"></a><a id="transfer_count_units_mebibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_MEBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in megabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_GIBIBYTES"></a><a id="transfer_count_units_gibibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_GIBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in gigabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_TEBIBYTES"></a><a id="transfer_count_units_tebibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_TEBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in terabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_PEBIBYTES"></a><a id="transfer_count_units_pebibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_PEBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in petabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_EXBIBYTES"></a><a id="transfer_count_units_exbibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_EXBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in exabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_NUMBER_BLOCKS"></a><a id="transfer_count_units_number_blocks"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_NUMBER_BLOCKS</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is not an exponent, but in units of logical block length.

</td>
</tr>
</table>

## Remarks
If <b>RECEIVE_TOKEN_INFORMATION_HEADER</b> is for a POPULATE TOKEN command operation, and the command completed successfully, a <a href="..\scsi\ns-scsi-receive_token_information_response_header.md">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a> structure will also be present after <b>SenseData</b> at an offset of <b>SenseDataFieldLength</b> from the beginning of the <b>SenseData</b> array. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure will contain the token created as a representation of data (ROD) for the range parameters sent with the command.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | scsi.h (include Scsi.h) |

## See Also

<a href="..\scsi\ns-scsi-receive_token_information_response_header.md">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RECEIVE_TOKEN_INFORMATION_HEADER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>