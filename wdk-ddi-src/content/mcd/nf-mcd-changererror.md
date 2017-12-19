---
UID: NF.mcd.ChangerError
title: ChangerError function
author: windows-driver-content
description: ChangerError performs device-specific error handling.
old-location: storage\changererror.htm
old-project: storage
ms.assetid: e2196971-47ad-4ac4-a3e9-c8f7f6b05321
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ChangerError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerError
req.alt-loc: mcd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# ChangerError function



## -description
<b>ChangerError</b> performs device-specific error handling. 



## -syntax

````
VOID ChangerError(
   PDEVICE_OBJECT      DeviceObject,
   PSCSI_REQUEST_BLOCK Srb,
   NTSTATUS            *Status,
   BOOLEAN             *Retry
);
````


## -parameters

### -param DeviceObject 

Pointer to the device object that represents the changer. 


### -param Srb 

Pointer to the SCSI request block for the operation that failed.


### -param Status 

Specifies the address of the STATUS_<i>XXX</i> code set by the system. The changer miniclass driver can change the status or leave it as is.


### -param Retry 

Pointer to a flag that indicates whether to retry the request. The changer miniclass driver can set this flag or leave it as is.


## -returns
This function does not return a value.


## -remarks
This routine is required.

If an SRB fails with a SCSI status of CHECK CONDITION, the SCSI class driver calls the changer class driver's <b>ChangerClassError</b> routine. <b>ChangerClassError</b> performs device-independent error handling and calls the changer miniclass driver's <b>ChangerError</b> routine.

<b>ChangerError</b> first checks <i>Srb</i><b>-&gt;SrbStatus</b> with SRB_STATUS_AUTOSENSE_VALID to make sure the sense data buffer is valid. If so, it checks the sense data in <i>Srb</i><b>-&gt;SenseInfoBuffer</b> to determine whether to update <i>*Status</i> with a more accurate STATUS_<i>XXX</i> code and/or set the <i>Retry</i> flag before returning to the changer class driver. The changer class driver's retry count determines whether the SRB is actually retried. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Mcd.h (include Mcd.h or Ntddchgr.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>