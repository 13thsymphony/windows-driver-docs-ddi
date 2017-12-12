---
UID: NE.ntddchgr._CHANGER_DEVICE_PROBLEM_TYPE
title: _CHANGER_DEVICE_PROBLEM_TYPE
author: windows-driver-content
description: The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the ChangerPerformDiagnostics routine.
old-location: storage\changer_device_problem_type.htm
old-project: storage
ms.assetid: 2ba267ad-cfd7-4a19-9ecb-16be9187406a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _CHANGER_DEVICE_PROBLEM_TYPE, CHANGER_DEVICE_PROBLEM_TYPE, *PCHANGER_DEVICE_PROBLEM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddchgr.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CHANGER_DEVICE_PROBLEM_TYPE
req.alt-loc: ntddchgr.h
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
---

# _CHANGER_DEVICE_PROBLEM_TYPE enumeration



## -description
The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the <a href="storage.changerperformdiagnostics">ChangerPerformDiagnostics</a> routine.



## -syntax

````
typedef enum _CHANGER_DEVICE_PROBLEM_TYPE { 
  DeviceProblemNone                  = 0,
  DeviceProblemHardware              = 1,
  DeviceProblemCHMError              = 2,
  DeviceProblemDoorOpen              = 3,
  DeviceProblemCalibrationError      = 4,
  DeviceProblemTargetFailure         = 5,
  DeviceProblemCHMMoveError          = 6,
  DeviceProblemCHMZeroError          = 7,
  DeviceProblemCartridgeInsertError  = 8,
  DeviceProblemPositionError         = 9,
  DeviceProblemSensorError           = 10,
  DeviceProblemCartridgeEjectError   = 11,
  DeviceProblemGripperError          = 12,
  DeviceProblemDriveError            = 13
} CHANGER_DEVICE_PROBLEM_TYPE, *PCHANGER_DEVICE_PROBLEM_TYPE;
````


## -enum-fields

### -field DeviceProblemNone

Indicates the device has no problem.


### -field DeviceProblemHardware

Indicates the device has had a hardware error.


### -field DeviceProblemCHMError

Indicates the Cartridge Handling Mechanism (CHM) has some problem.


### -field DeviceProblemDoorOpen

Indicates the changer's door is open.


### -field DeviceProblemCalibrationError

Indicates the changer has a calibration problem.


### -field DeviceProblemTargetFailure

Indicates a target failure has occurred.


### -field DeviceProblemCHMMoveError

Indicates the CHM is blocked and cannot move. 


### -field DeviceProblemCHMZeroError

Indicates the CHM could not define zero on one or more of its axis.


### -field DeviceProblemCartridgeInsertError

Indicates an error occurred while loading a cartridge in the drive.


### -field DeviceProblemPositionError

Indicates the CHM has a problem positioning itself to some point.


### -field DeviceProblemSensorError

Indicates the device's sensors are malfunctioning.


### -field DeviceProblemCartridgeEjectError

Indicates an error occurred while unloading a cartridge.


### -field DeviceProblemGripperError

Indicates the media gripper has a problem.


### -field DeviceProblemDriveError

Indicates the changer's drive is malfunctioning.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddchgr.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.changerperformdiagnostics">ChangerPerformDiagnostics</a>
</dt>
<dt>
<a href="storage.wmi_changer_problem_device_error">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_DEVICE_PROBLEM_TYPE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

