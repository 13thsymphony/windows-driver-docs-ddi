---
UID: NI:bthxddi.IOCTL_BTHX_WRITE_HCI
title: IOCTL_BTHX_WRITE_HCI
author: windows-driver-content
description: IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer.
old-location: bltooth\ioctl_bthx_hci_write.htm
old-project: bltooth
ms.assetid: 77BBF6AC-F5FA-4795-8898-6DC02983F573
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTHX_WRITE_HCI
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
req.typenames: *PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT
---

# IOCTL_BTHX_WRITE_HCI IOCTL



## -description

IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer.



IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer.



## -ioctlparameters

### -input-buffer
Profile drivers should use KMDF and its <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a> method to retrieve input parameters.  For example, to get the input buffer:

<code>Status = WdfRequestRetrieveInputMemory(_Request, &amp;ReqInMemory);</code>

The buffer describes a <a href="..\bthxddi\ns-bthxddi-_bthx_hci_read_write_context.md">BTHX_HCI_READ_WRITE_CONTEXT</a> structure that specifies the type of write and the data associated with the write. 

Refer to the WDK Bluetooth samples for more information.


### -input-buffer-length
The length of the buffer is the size of the <b>BTHX_HCI_READ_WRITE_CONTEXT</b> structure.


### -output-buffer
Profile drivers should use KMDF and its <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> method to retrieve input parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &amp;ReqOutMemory);</code>

The buffer describes a ULONG of the number of bytes written for the input data specified in the <b>BTHX_HCI_READ_WRITE_CONTEXT</b> structure. 

Refer to the WDK Bluetooth samples for more information.


### -output-buffer-length
The length of the buffer is the size of a ULONG.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the number of bytes in the Output Parameter.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

 


## -remarks
The Bluetooth stack sends IOCTL_BTHX_WRITE_HCI to write HCI ACL data and HCI command to the controller.

The input buffer points to a BTHX_HCI_READ_WRITE_CONTEXT structure whose <b>DataLen</b> member specifies the number of bytes in the <b>Data</b> member. The <b>Type</b> member is set based on whether the packet is a command packet or an ACL data packet.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>BthXDDI.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>