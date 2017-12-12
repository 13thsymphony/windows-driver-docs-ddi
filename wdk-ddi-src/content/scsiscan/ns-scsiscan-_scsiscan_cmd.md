---
UID: NS.SCSISCAN._SCSISCAN_CMD
title: _SCSISCAN_CMD
author: windows-driver-content
description: The SCSISCAN_CMD structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SCSISCAN_CMD.
old-location: image\scsiscan_cmd.htm
old-project: image
ms.assetid: 412c35b2-eb08-43a3-b776-053645806f5d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SCSISCAN_CMD, SCSISCAN_CMD, *PSCSISCAN_CMD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsiscan.h
req.include-header: Scsiscan.h, Srb.h, Scsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSISCAN_CMD
req.alt-loc: scsiscan.h
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
req.product: Windows 10 or later.
---

# _SCSISCAN_CMD structure



## -description
The SCSISCAN_CMD structure is used as a parameter to <a href="base.deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="..\scsiscan\ni-scsiscan-ioctl_scsiscan_cmd.md">IOCTL_SCSISCAN_CMD</a>.



## -syntax

````
typedef struct _SCSISCAN_CMD {
  ULONG  Reserved1;
  ULONG  Size;
  ULONG  SrbFlags;
  UCHAR  CdbLength;
  UCHAR  SenseLength;
  UCHAR  Reserved2;
  UCHAR  Reserved3;
  ULONG  TransferLength;
  UCHAR  Cdb[16];
  PUCHAR pSrbStatus;
  PUCHAR pSenseBuffer;
} SCSISCAN_CMD, *PSCSISCAN_CMD;
````


## -struct-fields

### -field Reserved1

Reserved. Do not use.


### -field Size

Caller-supplied size, in bytes, of the SCSISCAN_CMD structure.


### -field SrbFlags

Caller-supplied SRB_FLAGS-prefixed bit flag specifying the requested operation. Flags are defined in <i>srb.h</i>.


### -field CdbLength

Length, in bytes, of the <a href="wdkgloss.c#wdkgloss.cdb#wdkgloss.cdb"><i>CDB</i></a> contained in the <b>Cdb</b> member.


### -field SenseLength

Length, in bytes, of the sense buffer the <b>pSenseBuffer</b> member points to.


### -field Reserved2

Reserved. Do not use.


### -field Reserved3

Reserved. Do not use.


### -field TransferLength

Length, in bytes, of the buffer to be transferred. This should match the value specified for the <a href="base.deviceiocontrol">DeviceIoControl</a> function's <i>nOutBufferSize</i> parameter.


### -field Cdb

Caller-supplied <a href="wdkgloss.c#wdkgloss.cdb#wdkgloss.cdb"><i>CDB</i></a> data. (The CDB structure is declared in <i>scsi.h</i>.)


### -field pSrbStatus

Caller-supplied pointer that will receive one of the SRB_STATUS-prefixed status values defined in <i>srb.h</i>.


### -field pSenseBuffer

Caller-supplied pointer to a request-sense buffer, to be filled in by the kernel-mode driver.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Scsiscan.h (include Scsiscan.h, Srb.h, or Scsi.h)</dt>
</dl>
</td>
</tr>
</table>