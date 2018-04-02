---
UID: NF:usbcamdi.USBCAMD_Debug_LogEntry
title: USBCAMD_Debug_LogEntry function
author: windows-driver-content
description: The USBCAMD_Debug_LogEntry function is called by the camera minidriver to log debugging information to a file.
old-location: stream\usbcamd_debug_logentry.htm
old-project: stream
ms.assetid: a718cf3e-8359-4560-a88e-dd7789b61be6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: USBCAMD_Debug_LogEntry, USBCAMD_Debug_LogEntry function [Streaming Media Devices], stream.usbcamd_debug_logentry, usbcamdi/USBCAMD_Debug_LogEntry, usbcmdpr_6f6f6419-d845-4488-bd8d-70efa67357fa.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	usbcamd2.lib
-	usbcamd2.dll
api_name:
-	USBCAMD_Debug_LogEntry
product:
- Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# USBCAMD_Debug_LogEntry function
The <b>USBCAMD_Debug_LogEntry</b> function is called by the camera minidriver to log debugging information to a file.

## Syntax

```
void USBCAMD_Debug_LogEntry(
  CHAR  *Name,
  ULONG Info1,
  ULONG Info2,
  ULONG Info3
);
```

## Parameters

`Name`

Pointer to a <b>NULL</b>-terminated string containing the name of the file to write the log entry to.

`Info1`

Specifies the first information value to be written to the log file.

`Info2`

Specifies the second information value to be written to the log file.

`Info3`

Specifies the third information value to be written to the log file.


## Return Value

<b>USBCAMD_Debug_LogEntry </b>does not return a value.

## Remarks

The original USBCAMD does not call <b>USBCAMD_Debug_LogEntry</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **Library** | Usbcamd2.lib |