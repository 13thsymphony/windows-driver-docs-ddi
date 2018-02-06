---
UID: NC:hdaudio.PGET_WALL_CLOCK_REGISTER
title: PGET_WALL_CLOCK_REGISTER
author: windows-driver-content
description: The GetWallClockRegister routine retrieves a pointer to the wall clock register.The function pointer type for a GetWallClockRegister routine is defined as:
old-location: audio\getwallclockregister.htm
old-project: audio
ms.assetid: 4efe4b23-eb4f-4170-8d73-05cae2ba21c2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.getwallclockregister, GetWallClockRegister callback function [Audio Devices], GetWallClockRegister, PGET_WALL_CLOCK_REGISTER, PGET_WALL_CLOCK_REGISTER, hdaudio/GetWallClockRegister, aud-prop2_1600e03f-4be0-4a61-9596-7970ace3df2f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	hdaudio.h
apiname:
-	GetWallClockRegister
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PGET_WALL_CLOCK_REGISTER callback function
The <code>GetWallClockRegister</code> routine retrieves a pointer to the wall clock register.

The function pointer type for a <code>GetWallClockRegister</code> routine is defined as:

## Syntax

```
PGET_WALL_CLOCK_REGISTER PgetWallClockRegister;

void PgetWallClockRegister(
  PVOID _context,
  PULONG *Wallclock
)
{...}
```

## Parameters

`_context`

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

`*Wallclock`




## Return Value

None

## Remarks

For more information, see <a href="https://msdn.microsoft.com/6764affc-a4f0-4568-aa27-7f12e86b818b">Wall Clock and Link Position Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PGET_WALL_CLOCK_REGISTER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>