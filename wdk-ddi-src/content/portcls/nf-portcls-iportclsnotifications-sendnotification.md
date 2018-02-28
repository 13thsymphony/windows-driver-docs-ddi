---
UID: NF:portcls.IPortClsNotifications.SendNotification
title: IPortClsNotifications::SendNotification method
author: windows-driver-content
description: Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps.
old-location: audio\iportclsnotifications_sendnotification.htm
old-project: audio
ms.assetid: 0683C30D-0AAD-4859-BA30-908FA747CC35
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPortClsNotifications, IPortClsNotifications interface [Audio Devices], SendNotification method, IPortClsNotifications::SendNotification, SendNotification method [Audio Devices], SendNotification method [Audio Devices], IPortClsNotifications interface, SendNotification,IPortClsNotifications.SendNotification, audio.iportclsnotifications_sendnotification, portcls/IPortClsNotifications::SendNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1703 and later versions of Windows.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	IPortClsNotifications.SendNotification
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# SendNotification method
Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps.

## Syntax

````
NTSTATUS  SendNotification(
  [in] Const GUID*         NotificationId,
  [in] NotificationBuffer PPCNOTIFICATION* 
);
````

## Parameters

`NotificationId`

KSNOTIFICATIONID_AudioModule

`NotificationBuffer`




## Return Value

This function returns void.

## Remarks

Pointer to the PCNOTIFICATION structure to send to Audio Module clients.

The expected format of the payload is a <a href="..\ksmedia\ns-ksmedia-_ksaudiomodule_notification.md">KSAUDIOMODULE_NOTIFICATION</a> structure. The miniport driver can optionally send additional information immediately following the <b>KSAUDIOMODULE_NOTIFICATION</b> structure that will be untouched and sent to the Audio Module clients.



For more information about audio modules, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10, version 1703 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsNotifications::SendNotification method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>