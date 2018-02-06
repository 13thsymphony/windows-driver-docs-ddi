---
UID: NS:ksmedia.tagDEVCAPS
title: tagDEVCAPS
author: windows-driver-content
description: The DEVCAPS structure describes the capabilities of an external device.
old-location: stream\devcaps.htm
old-project: stream
ms.assetid: 4032ec5c-c98a-44f9-9c74-dc5ada308d33
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/DEVCAPS, tagDEVCAPS, stream.devcaps, ksmedia/PDEVCAPS, *PDEVCAPS, PDEVCAPS structure pointer [Streaming Media Devices], vidcapstruct_61cce92e-4f74-48ff-ae84-72579136a64f.xml, PDEVCAPS, DEVCAPS structure [Streaming Media Devices], DEVCAPS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	DEVCAPS
product: Windows
targetos: Windows
req.typenames: DEVCAPS, *PDEVCAPS
---

# tagDEVCAPS structure
The DEVCAPS structure describes the capabilities of an external device.

## Syntax
````
typedef struct tagDEVCAPS {
  LONG CanRecord;
  LONG CanRecordStrobe;
  LONG HasAudio;
  LONG HasVideo;
  LONG UsesFiles;
  LONG CanSave;
  LONG DeviceType;
  LONG TCRead;
  LONG TCWrite;
  LONG CTLRead;
  LONG IndexRead;
  LONG Preroll;
  LONG Postroll;
  LONG SyncAcc;
  LONG NormRate;
  LONG CanPreview;
  LONG CanMonitorSrc;
  LONG CanTest;
  LONG VideoIn;
  LONG AudioIn;
  LONG Calibrate;
  LONG SeekType;
  LONG SimulatedHardware;
} DEVCAPS, *PDEVCAPS;
````

## Members


`AudioIn`

Indicates the external device accepts audio as an input.

`Calibrate`

Indicates if the external device requires calibrating.

`CanMonitorSrc`

Specifies if the external device can monitor source.

`CanPreview`

Specifies if the external device can preview.

`CanRecord`

Specifies if the external device can record.

`CanRecordStrobe`

For multitrack devices. Specifies if the external device can record. Switches currently recording tracks off and selected nonrecording track into record.

`CanSave`

Specifies if the external device can save.

`CanTest`

Indicates the implementation of the external device allows testing of methods/parameters by setting the high bit of a parameter that makes sense. This is not implemented an always returns FALSE.

`CTLRead`

Specifies if the external device can read to a control track (nontimecode) target value.

`DeviceType`

Specifies the type of the external device. See Remarks.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_DEVTYPE_VCR

</td>
<td>
Video cassette recorder

</td>
</tr>
<tr>
<td>
ED_DEVTYPE_LASERDISC

</td>
<td>
Laserdisc player

</td>
</tr>
<tr>
<td>
ED_DEVTYPE_KEYBOARD

</td>
<td>
Keyboard

</td>
</tr>
<tr>
<td>
ED_DEVTYPE_CAMERA

</td>
<td>
Video camera

</td>
</tr>
<tr>
<td>
ED_DEVTYPE_VTR

</td>
<td>
Video tape recorder

</td>
</tr>
<tr>
<td>
ED_DEVTYPE_UNKNOWN

</td>
<td>
Unknown type

</td>
</tr>
</table>

`HasAudio`

Specifies if the external device has audio capabilities.

`HasVideo`

Specifies if the external device has video capabilities.

`IndexRead`

Specifies if the external device can read to an index (nontimecode) target value.

`NormRate`

Specifies the external device's normal frame rate.

`Postroll`

Specifies the external device's postroll time in the current time format.

`Preroll`

Specifies the external device's preroll time in the current time format.

`SeekType`

Specifies the type of seeking the external device is capable of. For example:
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_SEEK_PERFECT

</td>
<td>
Indicates device can seek to within 1 video frame without a signal break (like a DDR).

</td>
</tr>
<tr>
<td>
ED_SEEK_FAST

</td>
<td>
Indicates device can seek quick with a short break in signal.

</td>
</tr>
<tr>
<td>
ED_SEEK_SLOW

</td>
<td>
Indicates slow seeking (like a tape transport).

</td>
</tr>
</table>

`SimulatedHardware`

Must be set to zero.

`SyncAcc`

Indicates the external device's synchronization accuracy.

`TCRead`

Specifies if the external device can read timecodes.

`TCWrite`

Specifies if the external device can write timecodes.

`UsesFiles`

Specifies if the external device uses files.

`VideoIn`

Indicates the external device accepts video as an input.

## Remarks
Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

All members of the DEVCAPS structure are <b>TRUE</b>/<b>FALSE</b> unless otherwise specified.

The <b>DeviceType</b> member can be used by an application to detect the device type or its current operating mode. For example, it can return either ED_DEVTYPE_CAMERA or ED_DEVTYPE_VTR depending on a DV camcorder's mode of operation. Also, some DV devices may not be known and a device type of ED_DEVTYPE_UNKNOWN can be returned by the driver. This happens with some DV media converters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-ksproperty_extdevice_s.md">KSPROPERTY_EXTDEVICE_S</a>

<a href="..\ksmedia\ns-ksmedia-_timecode.md">TIMECODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20DEVCAPS structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>