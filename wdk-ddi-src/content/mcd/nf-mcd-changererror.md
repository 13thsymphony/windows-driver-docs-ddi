---
UID : NF:mcd.ChangerError
title : ChangerError function
author : windows-driver-content
description : ChangerError performs device-specific error handling.
old-location : storage\changererror.htm
old-project : storage
ms.assetid : e2196971-47ad-4ac4-a3e9-c8f7f6b05321
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ChangerError function [Storage Devices], mcd/ChangerError, chgrmini_5235b77f-51d1-4fa5-b68c-3e649aed829c.xml, ChangerError, storage.changererror
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : mcd.h
req.include-header : Mcd.h, Ntddchgr.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : LAMP_INTENSITY_WHITE
---


# ChangerError function
<b>ChangerError</b> performs device-specific error handling.

## Syntax

````
VOID ChangerError(
   PDEVICE_OBJECT      DeviceObject,
   PSCSI_REQUEST_BLOCK Srb,
   NTSTATUS            *Status,
   BOOLEAN             *Retry
);
````

## Parameters

`DeviceObject`

Pointer to the device object that represents the changer.

`Srb`

Pointer to the SCSI request block for the operation that failed.

`Status`

Specifies the address of the STATUS_<i>XXX</i> code set by the system. The changer miniclass driver can change the status or leave it as is.

`Retry`

Pointer to a flag that indicates whether to retry the request. The changer miniclass driver can set this flag or leave it as is.


## Return Value

This function does not return a value.

## Remarks

This routine is required.

If an SRB fails with a SCSI status of CHECK CONDITION, the SCSI class driver calls the changer class driver's <b>ChangerClassError</b> routine. <b>ChangerClassError</b> performs device-independent error handling and calls the changer miniclass driver's <b>ChangerError</b> routine.

<b>ChangerError</b> first checks <i>Srb</i><b>-&gt;SrbStatus</b> with SRB_STATUS_AUTOSENSE_VALID to make sure the sense data buffer is valid. If so, it checks the sense data in <i>Srb</i><b>-&gt;SenseInfoBuffer</b> to determine whether to update <i>*Status</i> with a more accurate STATUS_<i>XXX</i> code and/or set the <i>Retry</i> flag before returning to the changer class driver. The changer class driver's retry count determines whether the SRB is actually retried.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |