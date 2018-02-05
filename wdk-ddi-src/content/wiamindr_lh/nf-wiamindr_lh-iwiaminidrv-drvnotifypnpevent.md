---
UID : NF:wiamindr_lh.IWiaMiniDrv.drvNotifyPnpEvent
title : IWiaMiniDrv::drvNotifyPnpEvent method
author : windows-driver-content
description : The IWiaMiniDrv::drvNotifyPnpEvent method responds to the event received from the WIA service.
old-location : image\iwiaminidrv_drvnotifypnpevent.htm
old-project : image
ms.assetid : 55d6d93b-c20f-435b-ba99-2df26bd17240
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : IWiaMiniDrv, MiniDrv_7684a7e5-7ca5-4d20-a1a8-fc38400815ce.xml, IWiaMiniDrv::drvNotifyPnpEvent, drvNotifyPnpEvent method [Imaging Devices], IWiaMiniDrv interface, IWiaMiniDrv interface [Imaging Devices], drvNotifyPnpEvent method, drvNotifyPnpEvent method [Imaging Devices], drvNotifyPnpEvent, image.iwiaminidrv_drvnotifypnpevent, wiamindr_lh/IWiaMiniDrv::drvNotifyPnpEvent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wiamindr_lh.h
req.include-header : Wiamindr.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Me and in Windows XP and later.
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
req.lib : wiamindr_lh.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SCANWINDOW, *PSCANWINDOW
req.product : Windows 10 or later.
---


# drvNotifyPnpEvent method
The <b>IWiaMiniDrv::drvNotifyPnpEvent</b> method responds to the event received from the WIA service.

## Syntax

````
HRESULT drvNotifyPnpEvent(
  [in] const GUID  *pEventGuid,
  [in]       BSTR  bstrDeviceID,
  [in]       ULONG ulReserved
);
````

## Parameters

`pEventGUID`



`bstrDeviceID`

Specifies a string containing the device's unique identifier.

`ulReserved`

Is reserved for system use.


## Return Value

On success, the method should return S_OK. If the method fails, it should return a standard COM error code.

## Remarks

The WIA service notifies a WIA minidriver of a supported device event by calling the <b>IWiaMiniDrv::drvNotifyPnpEvent</b> method. In this method the minidriver implements the device-specific functionality needed to respond to the event.

If this method is called with *<i>pEventGuid</i> set to WIA_EVENT_CANCEL_IO device event (described in the Microsoft Windows SDK documentation), it should cancel all current I/O operations as soon as possible.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later. Available in Windows Me and in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** | wiamindr_lh.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543977">IWiaMiniDrv::drvGetCapabilities</a>

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvNotifyPnpEvent method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>