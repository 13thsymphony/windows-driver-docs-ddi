---
UID : NI:bthxddi.IOCTL_BTHX_READ_HCI
title : IOCTL_BTHX_READ_HCI
author : windows-driver-content
description : IOCTL_BTHX_READ_HCI is used to read Bluetooth ACL Data and Events from the transport layer.
old-location : bltooth\ioctl_bthx_hci_read.htm
old-project : bltooth
ms.assetid : 02CC3534-D319-40C1-A73C-DEFC1F5709F7
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : bthxddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_BTHX_READ_HCI
req.alt-loc : BthXDDI.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= PASSIVE_LEVEL
req.typenames : "*PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT"
---

# IOCTL_BTHX_READ_HCI IOCTL
IOCTL_BTHX_READ_HCI is used to read Bluetooth ACL Data and Events from the transport layer.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Profile drivers should use KMDF and its <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a> method to retrieve input parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveInputMemory(_Request, &amp;ReqInMemory);</code>

For more information, see the WDK Bluetooth samples.

### Input Buffer Length
The buffer describes a UCHAR that represents the type of read. The length of the buffer is the size of the UCHAR.

### Output Buffer
Profile drivers should use KMDF and its <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> method to retrieve input parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &amp;ReqOutMemory);</code>

For more information, see the WDK Bluetooth samples.

### Output Buffer Length
The 
       <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a <a href="..\bthxddi\ns-bthxddi-_bthx_hci_read_write_context.md">BTHX_HCI_READ_WRITE_CONTEXT</a> structure and additional data associated with the read. The  buffer must be large enough to hold the largest event or ACL Data packet, depending on its packet type.

For an event packet, it is FIELD_OFFSET(BTHX_HCI_READ_WRITE_CONTEXT, Data) +257 where 257 is the sum of a 2-byte event header and 255-byte event data.

For an ACL Data packet, it is FIELD_OFFSET(BTHX_HCI_READ_WRITE_CONTEXT, Data) + MaxAclTransferInSize where MaxAclTransferInSize is the value in BTHX_CAPABILITIES that is returned from the transport driver with IOCTL_BTHX_QUERY_CAPABILITIES.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The 
       <b>Information</b>  member of the STATUS_BLOCK structure is set to the number of bytes of data returned.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_CANCELLED

The IOCTL has been canceled.

    ## Remarks
        The input buffer points to the type of packet that is being read.

The output buffer points to a BTHX_HCI_READ_WRITE_CONTEXT structure whose <b>DataLen</b> member specifies the number of bytes in the <b>Data</b> member. The <b>Type</b> member must be set to the same as the Input packet type.

The <b>Information</b> member of the STATUS_BLOCK should be set to FIELD_OFFSET(BTHX_HCI_READ_WRITE_CONTEXT, Data) + <b>DataLen</b>.

The maximum size of the <b>Data</b> member for an ACL read is determined by <b>MaxAclTransferInSize</b>, specified in the BTHX_CAPABILITIES structure.  The maximum size of the <b>Data</b> member for an event is 255.

This IOCTL should return STATUS_SUCCESS only under normal operation. Transport-specific errors should not be returned.  The IOCTL should return STATUS_CANCELLED only if this IOCTL has been canceled.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | bthxddi.h |
| **IRQL** | <= PASSIVE_LEVEL |