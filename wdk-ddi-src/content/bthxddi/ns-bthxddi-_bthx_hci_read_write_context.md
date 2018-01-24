---
UID : NS:bthxddi._BTHX_HCI_READ_WRITE_CONTEXT
title : _BTHX_HCI_READ_WRITE_CONTEXT
author : windows-driver-content
description : The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.
old-location : bltooth\bthx_hci_read_write_context.htm
old-project : bltooth
ms.assetid : EC31A704-A264-4A77-B979-BFA59B42BA94
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _BTHX_HCI_READ_WRITE_CONTEXT, *PBTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthxddi.h
req.include-header : BthXDDI.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BTHX_HCI_READ_WRITE_CONTEXT
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
req.irql : <= DISPATCH_LEVEL
req.typenames : "*PBTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT"
---

# _BTHX_HCI_READ_WRITE_CONTEXT structure
The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for  the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.

## Syntax
````
typedef struct _BTHX_HCI_READ_WRITE_CONTEXT {
  ULONG DataLen;
  UCHAR Type;
  UCHAR Data[];
} BTHX_HCI_READ_WRITE_CONTEXT, *PBTHX_HCI_READ_WRITE_CONTEXT;
````

## Members

        
            `DataLen`

            The length, in bytes, of data in <b>Data</b>.
        
            `Type`

            The type of packetized data.

    ## Remarks
        The BTHX_HCI_READ_WRITE_CONTEXT structure is an input parameter to the <a href="..\bthxddi\ni-bthxddi-ioctl_bthx_write_hci.md">IOCTL_BTHX_HCI_WRITE IOCTL</a> and specifies the type of packet associated with the write. It also specifies the data to be written in the <b>Data</b> member.

This structure is also used as an output parameter for the <a href="..\bthxddi\ni-bthxddi-ioctl_bthx_read_hci.md">IOCTL_BTHX_HCI_READ</a> IOCTL and specifies the type of packet and the data associated with the read.

This structure is packed to 1-byte boundary.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthxddi.h (include BthXDDI.h) |