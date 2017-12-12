---
UID: NS.ISCSIOP._SCSIREPORTLUNS_OUT
title: _ScsiReportLuns_OUT
author: windows-driver-content
description: The ScsiReportLuns_OUT structure holds the output data for the ScsiReportLuns method.
old-location: storage\scsireportluns_out.htm
old-project: storage
ms.assetid: 6335705d-a900-456a-a882-f7f11bb485af
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _ScsiReportLuns_OUT, ScsiReportLuns_OUT, *PScsiReportLuns_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiReportLuns_OUT
req.alt-loc: iscsiop.h
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

# _ScsiReportLuns_OUT structure



## -description
The ScsiReportLuns_OUT structure holds the output data for the <a href="storage.scsireportluns">ScsiReportLuns</a> method.



## -syntax

````
typedef struct _ScsiReportLuns_OUT {
  ULONG Status;
  ULONG ResponseBufferSize;
  UCHAR ScsiStatus;
  UCHAR SenseBuffer[18];
  UCHAR ResponseBuffer[1];
} ScsiReportLuns_OUT, *PScsiReportLuns_OUT;
````


## -struct-fields

### -field Status

The status of the <b>ScsiReportLuns</b> method. This member will contain 0 if the REPORT LUNS operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the REPORT LUNS operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="storage.iscsi_status_qualifiers">ISCSI_STATUS_QUALIFIERS</a>.  


### -field ResponseBufferSize

The size, in bytes, of the buffer at <b>ResponseBuffer</b><i>.</i>


### -field ScsiStatus

The status of the SCSI REPORT LUNS command. 


### -field SenseBuffer

A buffer that holds the SCSI sense data that the SCSI REPORT LUNS command received. 


### -field ResponseBuffer

A buffer that holds the response data that the SCSI REPORT LUNS command received. 


## -remarks
You must implement this method.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.addconnectiontosession">AddConnectionToSession</a>
</dt>
<dt>
<a href="storage.iscsi_status_qualifiers">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="storage.logintotarget">LoginToTarget</a>
</dt>
<dt>
<a href="storage.scsireportluns">ScsiReportLuns</a>
</dt>
<dt>
<a href="storage.scsireportluns_in2">ScsiReportLuns_IN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReportLuns_OUT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

