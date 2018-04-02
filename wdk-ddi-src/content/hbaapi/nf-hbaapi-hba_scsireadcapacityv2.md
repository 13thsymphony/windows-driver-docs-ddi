---
UID: NF:hbaapi.HBA_ScsiReadCapacityV2
title: HBA_ScsiReadCapacityV2 function
author: windows-driver-content
description: The HBA_ScsiReadCapacityV2 routine sends a SCSI read capacity command to the indicated remote port.
old-location: storage\hba_scsireadcapacityv2.htm
old-project: storage
ms.assetid: 8347e1ef-1285-43a9-bea7-a9a59ec0dfd0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_ScsiReadCapacityV2, HBA_ScsiReadCapacityV2 routine [Storage Devices], fibreHBA_rtns_8ac08e6d-79aa-4eee-a352-aa8ff51ec85f.xml, hbaapi/HBA_ScsiReadCapacityV2, storage.hba_scsireadcapacityv2
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
-	HBA_ScsiReadCapacityV2
product:
- Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_ScsiReadCapacityV2 function
The <b>HBA_ScsiReadCapacityV2</b> routine sends a SCSI read capacity command to the indicated remote port.

## Syntax

```
HBA_STATUS HBA_API HBA_ScsiReadCapacityV2(
  IN HBA_HANDLE     HbaHandle,
  IN HBA_WWN        HbaPortWWN,
  IN HBA_WWN        DiscoveredPortWWN,
  IN HBA_UINT64     FcLUN,
  OUT void          *pRespBuffer,
  IN OUT HBA_UINT32 *pRespBufferSize,
  OUT HBA_UINT8     *pScsiStatus,
  OUT void          *pSenseBuffer,
  IN OUT HBA_UINT32 *pSenseBufferSize
);
```

## Parameters

`HbaHandle`

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA through which the SCSI read capacity command is sent.

`HbaPortWWN`

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port from which the SCSI inquiry command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

`DiscoveredPortWWN`

TBD

`FcLUN`

TBD

`pRespBuffer`

Pointer to a buffer that receives the output data of the SCSI read capacity command.

`pRespBufferSize`

Indicates the size, in bytes, of the buffer at <i>pRespBuffer</i>.

`pScsiStatus`

Pointer to a buffer that receives the SCSI status data.

`pSenseBuffer`

Pointer to a buffer that receives the SCSI sense data.

`pSenseBufferSize`

On input, indicates the size, in bytes, of the buffer at <i>pSenseBuffer</i>. On output, this member indicates the number of bytes of sense data returned.


## Return Value

The <b>HBA_ScsiReadCapacityV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_ScsiReadCapacityV2</b> returns one of the following values.

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
Returned if the complete payload of a reply to the SCSI read capacity command was successfully retrieved. 

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
Returned if the SCSI read capacity command could not be delivered without causing a SCSI overlapped command condition.

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