---
UID: NS:ntdddisk._IDEREGS
title: "_IDEREGS"
author: windows-driver-content
description: The IDEREGS structure is used to report the contents of the IDE controller registers.
old-location: storage\ideregs.htm
old-project: storage
ms.assetid: 20897336-e032-4aa7-be5f-47704c6d1d12
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PIDEREGS, LPIDEREGS structure pointer [Storage Devices], structs-IDE_aeab294c-9363-4207-bbcb-d9d442ab5c92.xml, IDEREGS, LPIDEREGS, ntdddisk/IDEREGS, IDEREGS structure [Storage Devices], PIDEREGS structure pointer [Storage Devices], _IDEREGS, *LPIDEREGS, ntdddisk/LPIDEREGS, storage.ideregs, *PIDEREGS, ntdddisk/PIDEREGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdddisk.h
apiname:
-	IDEREGS
product: Windows
targetos: Windows
req.typenames: IDEREGS, *PIDEREGS, *LPIDEREGS
---

# _IDEREGS structure
The IDEREGS structure is used to report the contents of the IDE controller registers.

## Syntax
````
typedef struct _IDEREGS {
  UCHAR bFeaturesReg;
  UCHAR bSectorCountReg;
  UCHAR bSectorNumberReg;
  UCHAR bCylLowReg;
  UCHAR bCylHighReg;
  UCHAR bDriveHeadReg;
  UCHAR bCommandReg;
  UCHAR bReserved;
} IDEREGS, *PIDEREGS, *LPIDEREGS;
````

## Members


`bCommandReg`

Holds the contents of the IDE command register.

`bCylHighReg`

Holds the contents of the IDE high-order cylinder register.

`bCylLowReg`

Holds the contents of the IDE low-order cylinder register.

`bDriveHeadReg`

Holds the contents of the IDE drive/head register.

`bFeaturesReg`

Holds the contents of the Features register. This register is used to specify Self-Monitoring Analysis and Reporting Technology (SMART) commands. This member can hold any of the following values:
<table>
<tr>
<th>Feature</th>
<th>Meaning</th>
</tr>
<tr>
<td>
READ_ATTRIBUTES

</td>
<td>
Retrieve the device attributes

</td>
</tr>
<tr>
<td>
READ_THRESHOLDS.

</td>
<td>
Retrieve threshold values that indicate when a drive is about to fail.

</td>
</tr>
<tr>
<td>
ENABLE_DISABLE_AUTOSAVE.

</td>
<td>
Enables the optional attribute autosave feature of the device when set to 1. Disables this feature when set to 0..

</td>
</tr>
<tr>
<td>
SAVE_ATTRIBUTE_VALUES.

</td>
<td>
Instructs the device to save its attribute values to the device's non-volatile memory.

</td>
</tr>
<tr>
<td>
EXECUTE_OFFLINE_DIAGS

</td>
<td>
Causes the device to begin collecting SMART data in off-line mode or execute a self-diagnostic test routine in either captive or off-line mode.

</td>
</tr>
<tr>
<td>
SMART_READ_LOG

</td>
<td>
Retrieves the indicated log.

</td>
</tr>
<tr>
<td>
SMART_WRITE_LOG

</td>
<td>
Writes the  indicated number of 512-byte data sectors to the indicated log.

</td>
</tr>
<tr>
<td>
ENABLE_SMART

</td>
<td>
Enables SMART functionality on the device.

</td>
</tr>
<tr>
<td>
DISABLE_SMART

</td>
<td>
Disables SMART functionality on the device.

</td>
</tr>
<tr>
<td>
RETURN_SMART_STATUS

</td>
<td>
Retrieves the reliability status of the device.

</td>
</tr>
<tr>
<td>
ENABLE_DISABLE_AUTO_OFFLINE

</td>
<td>
Enables offline mode when set to 1. Disables offline mode when 0.

</td>
</tr>
</table>

`bReserved`

Reserved for future use. Should always be zero.

`bSectorCountReg`

Holds the contents of the sector count register. IDE sector count register.

`bSectorNumberReg`

Holds the contents of the sector number register.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a>

<a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_ex.md">ATA_PASS_THROUGH_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDEREGS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>