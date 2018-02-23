---
UID: NE:sffdisk.SFFDISK_DCMD
title: SFFDISK_DCMD
author: windows-driver-content
description: The SFFDISK_DCMD enumeration identifies the type of Secure Digital (SD) card operation.
old-location: sd\sffdisk_dcmd.htm
old-project: SD
ms.assetid: 145e460e-6988-4e61-bb33-6f1b1df54629
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sffdisk/SFFDISK_DC_LOCK_CHANNEL, sffdisk/SFFDISK_DC_DEVICE_COMMAND, SFFDISK_DC_GET_VERSION, SFFDISK_DC_UNLOCK_CHANNEL, SFFDISK_DCMD, SFFDISK_DC_LOCK_CHANNEL, SFFDISK_DC_DEVICE_COMMAND, sffdisk/SFFDISK_DC_GET_VERSION, sd-structs_440acb4f-89ba-4ea0-9f8b-c7fd241dfe85.xml, SD.sffdisk_dcmd, sffdisk/SFFDISK_DCMD, SFFDISK_DCMD enumeration [Buses], sffdisk/SFFDISK_DC_UNLOCK_CHANNEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sffdisk.h
req.include-header: Sffdisk.h
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sffdisk.h
apiname:
-	SFFDISK_DCMD
product: Windows
targetos: Windows
req.typenames: SFFDISK_DCMD
req.product: Windows 10 or later.
---

# SFFDISK_DCMD Enumeration
The SFFDISK_DCMD enumeration identifies the type of Secure Digital (SD) card operation.

## Syntax
````
typedef enum  { 
  SFFDISK_DC_GET_VERSION     = 0,
  SFFDISK_DC_LOCK_CHANNEL    = 1,
  SFFDISK_DC_UNLOCK_CHANNEL  = 2,
  SFFDISK_DC_DEVICE_COMMAND  = 3
} SFFDISK_DCMD;
````

## Constants

<table>
            
                <tr>
                    <td>SFFDISK_DC_DEVICE_COMMAND</td>
                    <td>The operation executes a device command.</td>
                </tr>
            
                <tr>
                    <td>SFFDISK_DC_GET_VERSION</td>
                    <td>The operations retrieves the version of the card.</td>
                </tr>
            
                <tr>
                    <td>SFFDISK_DC_LOCK_CHANNEL</td>
                    <td>The operation locks the interface channel.</td>
                </tr>
            
                <tr>
                    <td>SFFDISK_DC_UNLOCK_CHANNEL</td>
                    <td>The operation unlocks the interface channel.</td>
                </tr>
</table>

## Remarks

Applications that submit IOCTL_SFFDISK_DEVICE_COMMAND requests to the SD stack use this enumeration to specify the type of operation. The application must assign one of the values of this enumeration to the <b>Command</b> member of the <a href="https://msdn.microsoft.com/68205c17-5ff6-45a3-83c7-e106b314f9a5">SFFDISK_DEVICE_COMMAND_DATA</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sffdisk.h (include Sffdisk.h) |

## See Also

<a href="https://msdn.microsoft.com/68205c17-5ff6-45a3-83c7-e106b314f9a5">SFFDISK_DEVICE_COMMAND_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SFFDISK_DCMD enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>