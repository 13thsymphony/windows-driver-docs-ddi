---
UID : NS:ksmedia._KSAUDIOMODULE_NOTIFICATION
title : _KSAUDIOMODULE_NOTIFICATION
author : windows-driver-content
description : The KSAUDIOMODULE_NOTIFICATION structure describes the properties associated with audio modules change notification.
old-location : audio\ksaudiomodule_notification.htm
old-project : audio
ms.assetid : 92A9462C-0E8C-4012-9374-3437BB220502
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ksmedia/PKSAUDIOMODULE_NOTIFICATION, PKSAUDIOMODULE_NOTIFICATION structure pointer [Audio Devices], KSAUDIOMODULE_NOTIFICATION, ksmedia/KSAUDIOMODULE_NOTIFICATION, *PKSAUDIOMODULE_NOTIFICATION, PKSAUDIOMODULE_NOTIFICATION, _KSAUDIOMODULE_NOTIFICATION, audio.ksaudiomodule_notification, KSAUDIOMODULE_NOTIFICATION structure [Audio Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1703
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
req.typenames : KSAUDIOMODULE_NOTIFICATION, *PKSAUDIOMODULE_NOTIFICATION
---

# _KSAUDIOMODULE_NOTIFICATION structure
The <b>KSAUDIOMODULE_NOTIFICATION</b> structure describes the  properties associated with audio  modules change notification.

## Syntax
````
typedef struct _KSAUDIOMODULE_NOTIFICATION {
  union {
    struct {
      GUID  DeviceId;
      GUID  ClassId;
      ULONG InstanceId;
      ULONG Reserved;
    } ProviderId;
    LONGLONG  Alignment;
  };
} KSAUDIOMODULE_NOTIFICATION, *PKSAUDIOMODULE_NOTIFICATION;
````

## Members


## Remarks
The Audio module notification KSNOTIFICATIONID_AudioModule is defined in Ksmedia.h as shown here. 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>// 
// Audio module notification definitions. 
// 

#define STATIC_KSNOTIFICATIONID_AudioModule \ 
    0x9C2220F0, 0xD9A6, 0x4D5C, 0xA0, 0x36, 0x57, 0x38, 0x57, 0xFD, 0x50, 0xD2 

DEFINE_GUIDSTRUCT("9C2220F0-D9A6-4D5C-A036-573857FD50D2", KSNOTIFICATIONID_AudioModule); 

#define KSNOTIFICATIONID_AudioModule DEFINE_GUIDNAMED(KSNOTIFICATIONID_AudioModule)</pre>
</td>
</tr>
</table></span></div>

For more information about audio modules, see  <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |