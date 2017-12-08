---
UID: NS.bthxddi._BTHX_HCI_READ_WRITE_CONTEXT
title: BTHX_HCI_READ_WRITE_CONTEXT
author: windows-driver-content
description: The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.
old-location: bltooth\bthx_hci_read_write_context.htm
old-project: bltooth
ms.assetid: EC31A704-A264-4A77-B979-BFA59B42BA94
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: BTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT, *PBTHX_HCI_READ_WRITE_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthxddi.h
req.include-header: BthXDDI.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTHX_HCI_READ_WRITE_CONTEXT
req.alt-loc: BthXDDI.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# BTHX_HCI_READ_WRITE_CONTEXT structure



## -description
<p>The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for  the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.</p>


## -syntax

````
typedef struct _BTHX_HCI_READ_WRITE_CONTEXT {
  ULONG DataLen;
  UCHAR Type;
  UCHAR Data[];
} BTHX_HCI_READ_WRITE_CONTEXT, *PBTHX_HCI_READ_WRITE_CONTEXT;
````


## -struct-fields
<dl>

### -field DataLen

<dd>
<p>The length, in bytes, of data in <b>Data</b>.</p>
</dd>

### -field Type

<dd>
<p>The type of packetized data.</p>
</dd>

### -field Data[]

<dd>
<p>Actual data to be read/written.</p>
</dd>
</dl>

## -remarks
<p>The BTHX_HCI_READ_WRITE_CONTEXT structure is an input parameter to the <a href="..\bthxddi\ni-bthxddi-ioctl-bthx-write-hci.md">IOCTL_BTHX_HCI_WRITE IOCTL</a> and specifies the type of packet associated with the write. It also specifies the data to be written in the <b>Data</b> member.</p>

<p>This structure is also used as an output parameter for the <a href="..\bthxddi\ni-bthxddi-ioctl-bthx-read-hci.md">IOCTL_BTHX_HCI_READ</a> IOCTL and specifies the type of packet and the data associated with the read.</p>

<p>This structure is packed to 1-byte boundary.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Supported starting with  Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>BthXDDI.h (include BthXDDI.h)</dt>
</dl>
</td>
</tr>
</table>