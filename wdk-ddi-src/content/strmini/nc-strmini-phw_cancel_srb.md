---
UID : NC:strmini.PHW_CANCEL_SRB
title : PHW_CANCEL_SRB
author : windows-driver-content
description : The class driver calls the minidriver's StrMiniCancelPacket routine to signal that a stream request has been canceled.
old-location : stream\strminicancelpacket.htm
old-project : stream
ms.assetid : e64c00dd-4eef-4e1e-abb0-8263088f6dc6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.strminicancelpacket, StrMiniCancelPacket routine [Streaming Media Devices], StrMiniCancelPacket, PHW_CANCEL_SRB, PHW_CANCEL_SRB, strmini/StrMiniCancelPacket, strmini-routines_976ab3d0-d8aa-4121-a0a8-b37d08a07219.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : strmini.h
req.include-header : Strmini.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR"
req.product : Windows 10 or later.
---


# PHW_CANCEL_SRB callback function
The class driver calls the minidriver's <i>StrMiniCancelPacket</i> routine to signal that a stream request has been canceled.

## Syntax

```
PHW_CANCEL_SRB PhwCancelSrb;

void PhwCancelSrb(
  IN PHW_STREAM_REQUEST_BLOCK SRB
)
{...}
```

## Parameters

`SRB`




## Return Value

None

## Remarks

The minidriver specifies this routine in the <b>HwCancelPacket</b> member of its <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. The minidriver passes this structure to the class driver when it registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.

Minidrivers that rely on the class driver to handle synchronization should, once they have successfully canceled a request, signal to the class driver that they are ready for another request by using <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a> or <a href="..\strmini\nf-strmini-streamclassdevicenotification.md">StreamClassDeviceNotification</a> with the appropriate <b>ReadyForNext</b><i>Xxx</i><b>Request</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | strmini.h (include Strmini.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |