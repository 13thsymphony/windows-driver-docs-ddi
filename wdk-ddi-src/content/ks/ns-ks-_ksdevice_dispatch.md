---
UID : NS:ks._KSDEVICE_DISPATCH
title : _KSDEVICE_DISPATCH
author : windows-driver-content
description : The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.
old-location : stream\ksdevice_dispatch.htm
old-project : stream
ms.assetid : 1ae7af1d-5e1c-4728-82c5-efc8d60b5df6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PKSDEVICE_DISPATCH, avstruct_7ceb03b7-6973-46bd-ad3e-32fdce7f4f11.xml, ks/PKSDEVICE_DISPATCH, KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH, ks/KSDEVICE_DISPATCH, PKSDEVICE_DISPATCH structure pointer [Streaming Media Devices], stream.ksdevice_dispatch, _KSDEVICE_DISPATCH, KSDEVICE_DISPATCH structure [Streaming Media Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames : KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH
---

# _KSDEVICE_DISPATCH structure
The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.

## Syntax
````
typedef struct _KSDEVICE_DISPATCH {
  PFNKSDEVICECREATE            Add;
  PFNKSDEVICEPNPSTART          Start;
  PFNKSDEVICE                  PostStart;
  PFNKSDEVICEIRP               QueryStop;
  PFNKSDEVICEIRPVOID           CancelStop;
  PFNKSDEVICEIRPVOID           Stop;
  PFNKSDEVICEIRP               QueryRemove;
  PFNKSDEVICEIRPVOID           CancelRemove;
  PFNKSDEVICEIRPVOID           Remove;
  PFNKSDEVICEQUERYCAPABILITIES QueryCapabilities;
  PFNKSDEVICEIRPVOID           SurpriseRemoval;
  PFNKSDEVICEQUERYPOWER        QueryPower;
  PFNKSDEVICESETPOWER          SetPower;
  PFNKSDEVICEIRP               QueryInterface;
} KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH;
````

## Members


## Remarks
In describing a device with the <a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a> structure, clients include a pointer to a dispatch table defined by this structure. Any member of this structure may be <b>NULL</b> indicating that the minidriver receives no notification for that particular message.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDEVICE_DISPATCH structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>