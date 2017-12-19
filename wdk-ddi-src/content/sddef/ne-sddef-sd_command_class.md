---
UID: NE.sddef.SD_COMMAND_CLASS
title: SD_COMMAND_CLASS
author: windows-driver-content
description: The SD_COMMAND_CLASS enumeration lists the classes of Secure Digital (SD) card commands.
old-location: sd\sd_command_class.htm
old-project: SD
ms.assetid: 2c82db4c-70b1-4601-a0b0-23b1f53e3503
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SD_COMMAND_CLASS, SD_COMMAND_CLASS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sddef.h
req.include-header: Sddef.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SD_COMMAND_CLASS
req.alt-loc: sddef.h
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

# SD_COMMAND_CLASS enumeration



## -description
The SD_COMMAND_CLASS enumeration lists the classes of Secure Digital (SD) card commands.



## -syntax

````
typedef enum  { 
  SDCC_STANDARD  = 0,
  SDCC_APP_CMD   = 1
} SD_COMMAND_CLASS;
````


## -enum-fields

### -field SDCC_STANDARD

Indicates an SD card command from the standard command set. This command set includes command codes 0 to 63.


### -field SDCC_APP_CMD

Indicates an SD command from the application command set. This command set includes command codes 0 to 63, preceded by the application command escape code 55.

SD card drivers should not issue CMD55 (APP_CMD) commands through the SD bus interface. The bus driver will automatically issue the CMD55 command on behalf of the SD card driver when the command class is SDCC_APP_CMD.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Sddef.h (include Sddef.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/7c49c394-d0b3-4594-a623-0a13825bdcec">SDCMD_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SD_COMMAND_CLASS enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

