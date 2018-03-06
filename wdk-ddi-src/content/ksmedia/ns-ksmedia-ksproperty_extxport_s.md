---
UID: NS:ksmedia.KSPROPERTY_EXTXPORT_S
title: KSPROPERTY_EXTXPORT_S
author: windows-driver-content
description: The KSPROPERTY_EXTXPORT_S structure describes an external transport and its capabilities.
old-location: stream\ksproperty_extxport_s.htm
old-project: stream
ms.assetid: 01132969-b459-4110-a067-fda6c7ee5510
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_EXTXPORT_S, KSPROPERTY_EXTXPORT_S, KSPROPERTY_EXTXPORT_S structure [Streaming Media Devices], PKSPROPERTY_EXTXPORT_S, PKSPROPERTY_EXTXPORT_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_EXTXPORT_S, ksmedia/PKSPROPERTY_EXTXPORT_S, stream.ksproperty_extxport_s, vidcapstruct_9cd12be8-0378-481b-80e3-81b3decc1823.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	KSPROPERTY_EXTXPORT_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_EXTXPORT_S, *PKSPROPERTY_EXTXPORT_S
---

# KSPROPERTY_EXTXPORT_S structure
The KSPROPERTY_EXTXPORT_S structure describes an external transport and its capabilities.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  union {
    ULONG           Capabilities;
    ULONG           SignalMode;
    ULONG           LoadMedium;
    MEDIUM_INFO     MediumInfo;
    TRANSPORT_STATE XPrtState;
    struct {
      BYTE frame;
      BYTE second;
      BYTE minute;
      BYTE hour;
    } Timecode;
    DWORD           dwTimecode;
    DWORD           dwAbsTrackNumber;
    struct {
      ULONG PayloadSize;
      BYTE  Payload[512];
    } RawAVC;
  } u;
} KSPROPERTY_EXTXPORT_S, *PKSPROPERTY_EXTXPORT_S;
````

## Members


`Property`

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

`u`

#### Capabilities

Specifies the capabilities of the external transport. For example ED_TRANSCAP_CAN_EJECT, ED_TRANSCAP_CAN_PLAY_BACKWARDS, or ED_TRANSCAP_CAN_BUMP_PLAY. See Remarks.



#### SignalMode

Specifies the signal mode of the external transport. For example ED_TRANSBASIC_SIGNAL_525_60_SD, ED_TRANSBASIC_SIGNAL_MPEG2TS or ED_TRANSBASIC_SIGNAL_0625_50_MPEG. See Remarks



#### LoadMedium

Specifies load medium. For example eject, open tray, close tray.



#### MediumInfo

Describes the medium info.



#### XPrtState

Describes the external transports state.



#### dwTimecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.



#### dwAbsTrackNumber

Specifies the absolute track number. This member is defined for future use.

## Remarks
Any ED_TRANSCAP_Xxx or ED_TRANSBASIC_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="..\ksmedia\ns-ksmedia-ksproperty_extxport_node_s.md">KSPROPERTY_EXTXPORT_NODE_S</a>



<a href="..\ksmedia\ns-ksmedia-medium_info.md">MEDIUM_INFO</a>



<a href="..\ksmedia\ns-ksmedia-transport_state.md">TRANSPORT_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_EXTXPORT_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>