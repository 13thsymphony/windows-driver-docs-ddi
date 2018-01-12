---
UID: NF:srb.ScsiPortQuerySystemTime
title: ScsiPortQuerySystemTime function
author: windows-driver-content
description: The ScsiPortQuerySystemTime routine obtains the current system time.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportquerysystemtime.htm
old-project: storage
ms.assetid: 6f6afe6d-8f57-4c08-97ea-b327622a4e39
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiPortQuerySystemTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortQuerySystemTime
req.alt-loc: Scsiport.lib,Scsiport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Scsiport.lib
req.dll: 
req.irql: Any level
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# ScsiPortQuerySystemTime function



## -description
The <b>ScsiPortQuerySystemTime</b> routine obtains the current system time.



## -syntax

````
VOID ScsiPortQuerySystemTime(
  _Out_ PLARGE_INTEGER CurrentTime
);
````


## -parameters

### -param CurrentTime [out]

Pointer to the current time, on return. 


## -returns
None 


## -remarks
The system time returned in <i>CurrentTime</i> is the number of 100-nanosecond intervals that have elapsed since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. 


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
<dt>Srb.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Scsiport.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>