---
UID: NF:hbaapi.HBA_ScsiInquiryV2
title: HBA_ScsiInquiryV2 function
author: windows-driver-content
description: The HBA_ScsiInquiryV2 routine sends a SCSI inquiry command to the specified remote port.
old-location: storage\hba_scsiinquiryv2.htm
old-project: storage
ms.assetid: ba82c6f1-f310-4258-8867-8309845320cc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_ScsiInquiryV2, HBA_ScsiInquiryV2 routine [Storage Devices], fibreHBA_rtns_eb1e2682-5317-4ea3-a3e2-2d1db00c5f9b.xml, hbaapi/HBA_ScsiInquiryV2, storage.hba_scsiinquiryv2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_ScsiInquiryV2
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_ScsiInquiryV2 function
The <b>HBA_ScsiInquiryV2</b> routine sends a SCSI inquiry command to the specified remote port.

## Syntax

```
HBA_STATUS HBA_API HBA_ScsiInquiryV2(
  IN HBA_HANDLE     HbaHandle,
  IN HBA_WWN        HbaPortWWN,
  IN HBA_WWN        DiscoveredPortWWN,
  IN HBA_UINT64     FcLUN,
  IN HBA_UINT8      CDB_Byte1,
  IN HBA_UINT8      CDB_Byte2,
  OUT void          *pRespBuffer,
  IN OUT HBA_UINT32 *pRespBufferSize,
  OUT HBA_UINT8     *pScsiStatus,
  OUT void          *pSenseBuffer,
  IN OUT HBA_UINT32 *pSenseBufferSize
);
```

## Parameters

`HbaHandle`

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA through which the SCSI inquiry command is sent.

`HbaPortWWN`

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port from which the SCSI inquiry command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

`DiscoveredPortWWN`

TBD

`FcLUN`

TBD

`CDB_Byte1`

Contains the value to insert in the first byte of the command descriptor block (CDB) of the SCSI inquiry command. This member must have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
Indicates that the SCSI inquiry command should request the standard SCSI INQUIRY data. 

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Indicates that the SCSI inquiry command should request the vital product data specified by <i>CDB_Byte2</i>. 

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Indicates that the SCSI inquiry command should request command support data (CmdDt) specified in <i>CDB_Byte2</i>. 

</td>
</tr>
</table>

`CDB_Byte2`

Contains the value to insert in the third byte of the command descriptor block (CDB) of the SCSI inquiry command. This member must have one of the following values:

<table>
<tr>
<th>Value in <i>CDB_Byte1</i></th>
<th>Meaning of the value in <i>CDB_Byte2</i></th>
</tr>
<tr>
<td>
1

</td>
<td>
Indicates that <i>CDB_Byte2 </i>contains the page number of the vital product data to retrieve. 

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Indicates that <i>CDB_Byte2 </i>contains the operation code of the command support data to retrieve. 

</td>
</tr>
</table>

`pRespBuffer`

Pointer to a buffer that receives the output data of the SCSI inquiry command.

`pRespBufferSize`

Indicates the size, in bytes, of the buffer at <i>pRespBuffer</i>.

`pScsiStatus`

Pointer to a buffer that receives the SCSI status data.

`pSenseBuffer`

Pointer to a buffer that receives the SCSI sense data.

`pSenseBufferSize`

On input, indicates the size, in bytes, of the buffer at <i>pSenseBuffer</i>. On output, this member indicates the number of bytes of sense data returned.


## Return Value

The <b>HBA_ScsiInquiryV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_ScsiInquiryV2</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the complete payload of a reply to the SCSI inquiry command was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_A_TARGET</b></dt>
</dl>
</td>
<td width="60%">
Returned if the specified remote port referenced by <i>discoveredPortWWN </i>does not have SCSI target functionality.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_TARGET_BUSY</b></dt>
</dl>
</td>
<td width="60%">
Returned if the SCSI inquiry command could not be delivered without causing a SCSI overlapped command condition.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_SCSI_CHECK_CONDITION</b></dt>
</dl>
</td>
<td width="60%">
Returned if a SCSI check condition occurred and SCSI send data is provided in the buffer at <i>pSenseBuffer</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the SCSI inquiry command. 

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>