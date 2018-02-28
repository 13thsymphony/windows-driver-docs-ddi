---
UID: NS:ntddpcm._PCMCIA_SOCKET_INFORMATION
title: "_PCMCIA_SOCKET_INFORMATION"
author: windows-driver-content
description: The PCMCIA_SOCKET_INFORMATION structure is used in conjunction with the IOCTL_SOCKET_INFORMATION request to retrieve socket configuration and state data.
old-location: pcmcia\pcmcia_socket_information.htm
old-project: PCMCIA
ms.assetid: 53881aca-e49c-43e9-b68e-b91a1868e3f5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPCMCIA_SOCKET_INFORMATION, PCMCIA.pcmcia_socket_information, PCMCIA_SOCKET_INFORMATION, PCMCIA_SOCKET_INFORMATION structure [Buses], PPCMCIA_SOCKET_INFORMATION, PPCMCIA_SOCKET_INFORMATION structure pointer [Buses], _PCMCIA_SOCKET_INFORMATION, memcdref_b118ae5c-5dc5-4919-809d-5cfe5b25598f.xml, ntddpcm/PCMCIA_SOCKET_INFORMATION, ntddpcm/PPCMCIA_SOCKET_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddpcm.h
api_name:
-	PCMCIA_SOCKET_INFORMATION
product: Windows
targetos: Windows
req.typenames: PCMCIA_SOCKET_INFORMATION, *PPCMCIA_SOCKET_INFORMATION
---

# _PCMCIA_SOCKET_INFORMATION structure
The PCMCIA_SOCKET_INFORMATION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537275">IOCTL_SOCKET_INFORMATION</a> request to retrieve socket configuration and state data.

## Syntax
````
typedef struct _PCMCIA_SOCKET_INFORMATION {
  USHORT Socket;
  USHORT TupleCrc;
  UCHAR  Manufacturer[MANUFACTURER_NAME_LENGTH];
  UCHAR  Identifier[DEVICE_IDENTIFIER_LENGTH];
  UCHAR  DriverName[DRIVER_NAME_LENGTH];
  UCHAR  DeviceFunctionId;
  UCHAR  Reserved;
  UCHAR  CardInSocket;
  UCHAR  CardEnabled;
  ULONG  ControllerType;
} PCMCIA_SOCKET_INFORMATION, *PPCMCIA_SOCKET_INFORMATION;
````

## Members


`CardEnabled`

Indicates that the card is enabled.

`CardInSocket`

Indicates that there is a card present in the socket.

`ControllerType`

Indicates the controller type. Some common controller types are defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537600">PCMCIA_CONTROLLER_CLASS</a> enumeration.

`DeviceFunctionId`

Indicates the type of PC Card or CardBus card. This value can be one of the following.

<table>
<tr>
<th>PC Card Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCCARD_TYPE_MULTIFUNCTION

</td>
<td>
Multifunction card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_MEMORY

</td>
<td>
Memory card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_SERIAL

</td>
<td>
Serial port card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_PARALLEL

</td>
<td>
Parallel port card.

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_ATA

</td>
<td>
Disk controller card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_VIDEO

</td>
<td>
Video controller card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_NETWORK

</td>
<td>
Network controller card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_AIMS

</td>
<td>
Auto-increment mass storage card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_SCSI_BRIDGE

</td>
<td>
SCSI bridge card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_SECURITY

</td>
<td>
Security card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_MULTIFUNCTION3

</td>
<td>
Multifunction 3.0 PC Card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_FLASH_MEMORY

</td>
<td>
Flash memory card. 

</td>
</tr>
<tr>
<td>
PCCARD_TYPE_MODEM

</td>
<td>
Modem card. 

</td>
</tr>
</table>

`DriverName`

Contains the name of the PC Card or CardBus card device driver.

`Identifier`

Contains the device ID of the PC Card or CardBus card.

`Manufacturer`

Indicates the manufacturer of the PC Card or CardBus card.

`Reserved`

Reserved.

`Socket`

Indicates the socket number.

`TupleCrc`

Contains a 16-bit CRC that is concatenated with the PCMCIA prefix, the manufacturer-name string, the product-name string, and the instance value for the card to produce the device ID for a PC Card or CardBus card. For more information about PCMCIA device IDs, see <a href="https://msdn.microsoft.com/7eaf6372-a9cc-4714-8955-52653ec57141">Identifiers for PCMCIA Devices</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpcm.h (include Ntddpcm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537275">IOCTL_SOCKET_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_SOCKET_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>