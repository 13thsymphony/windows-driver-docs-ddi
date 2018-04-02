---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
title: tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
author: windows-driver-content
description: The EV Compensation Control provides for exposure control that is adjusted by increments of EV compensation steps.
old-location: stream\kscamera_extendedprop_evcompensation.htm
old-project: stream
ms.assetid: C9CF39F2-5081-4B99-BFD1-9F7130B27369
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, KSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, ksmedia/PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, stream.kscamera_extendedprop_evcompensation, tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
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
-	Ksmedia.h
api_name:
-	KSCAMERA_EXTENDEDPROP_EVCOMPENSATION
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, *PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
---

# tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure
The <i>EV Compensation Control</i> provides for exposure control that is adjusted by increments of EV compensation steps.

## Syntax
```
typedef struct tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION {
  ULONG     Mode;
  LONG      Min;
  LONG      Max;
  LONG      Value;
  ULONGLONG Reserved;
} *PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, KSCAMERA_EXTENDEDPROP_EVCOMPENSATION;
```

## Members


`Mode`

Not used. Set to 0.

`Min`

The minimum EV compensation supported. This is an absolute EV value.

`Max`

The maximum EV compensation supported. This is an absolute EV value.

`Value`

EV Compensation in units of steps  selected in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/dn567563">KSCAMERA_EXTENDEDPROP_HEADER</a>.

`Reserved`

Reserved.

## Remarks
<b>Value</b> is assigned a stepping increment. For example, if <b>Min</b> = -2, <b>Max</b> = 2 and the compensation stepping is set as one third step (incremented in units of 1/3 EV compensation), the valid values of EV compensation are -2, -1 2/3, -1 1/3, -1, -2/3, -1/3, 0, 1/3, 2/3, 1, 1 1/3, 1 2/3, and 2.  This corresponds to the <b>Value</b> field as -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5, 6. As an example, if  <b>Value</b> = -6, then EV compensation = -2, or (-6 * 1/3) = -2.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1. Available starting with Windows 8.1. |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn567563">KSCAMERA_EXTENDEDPROP_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn567572">KSPROPERTY_CAMERACONTROL_EXTENDED_EVCOMPENSATION</a>