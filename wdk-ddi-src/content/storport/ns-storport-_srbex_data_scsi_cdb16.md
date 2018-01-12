---
UID: NS:storport._SRBEX_DATA_SCSI_CDB16
title: _SRBEX_DATA_SCSI_CDB16
author: windows-driver-content
description: The SRBEX_DATA_SCSI_CDB16 structure contains the extended SRB data for a 16-byte SCSI command data block (CDB).
old-location: storage\srbex_data_scsi_cdb16.htm
old-project: storage
ms.assetid: 168AC5F4-652B-405C-BE41-CD416A66FB74
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SRBEX_DATA_SCSI_CDB16, *PSRBEX_DATA_SCSI_CDB16, SRBEX_DATA_SCSI_CDB16
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRBEX_DATA_SCSI_CDB16
req.alt-loc: Storport.h
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
req.typenames: *PSRBEX_DATA_SCSI_CDB16, SRBEX_DATA_SCSI_CDB16
req.product: Windows 10 or later.
---

# _SRBEX_DATA_SCSI_CDB16 structure



## -description
The <b>SRBEX_DATA_SCSI_CDB16</b> structure contains the extended SRB data for a 16-byte SCSI command data block (CDB).



## -syntax

````
typedef struct _SRBEX_DATA_SCSI_CDB16 {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               ScsiStatus;
  UCHAR               SenseInfoBufferLength;
  ULONG               CdbLength;
  UCHAR               Reserved;
  ULONG               Reserved1;
  PVOID POINTER_ALIGN SenseInfoBuffer;
  UCHAR POINTER_ALIGN Cdb[16];
} SRBEX_DATA_SCSI_CDB16, *PSRBEX_DATA_SCSI_CDB16;
````


## -struct-fields

### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeScsiCdb16</b>.


### -field Length

Length of the data in this structure, in bytes, starting with the <b>ScsiStatus</b> member. Set to SRBEX_DATA_SCSI_CDB16_LENGTH.


### -field ScsiStatus

The SCSI status code returned for the submitted SRB.


### -field SenseInfoBufferLength

The length of the sense information returned in the buffer pointed to by <b>SenseInfoBuffer</b>.


### -field CdbLength

The length of the CDB data, in bytes, of the <b>Cdb</b> array.


### -field Reserved

This member is reserved. Set to 0.


### -field Reserved1

This member is reserved. Set to 0.


### -field SenseInfoBuffer

A pointer to a buffer containing any returned sense information.


### -field Cdb

The 16-byte CDB buffer.


## -remarks
This structure is used to submit an extended SRB data for a CDB of 16 bytes or less.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h or Srb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\storport\ns-storport-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a>
</dt>
<dt>
<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA_SCSI_CDB16 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

