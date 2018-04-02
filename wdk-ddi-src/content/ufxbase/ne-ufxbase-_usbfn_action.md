---
UID: NE:ufxbase._USBFN_ACTION
title: "_USBFN_ACTION"
author: windows-driver-content
description: Defines special actions UFX should take when the client driver calls the UfxDevicePortDetectCompleteEx function.
old-location: buses\usbfn_action.htm
old-project: usbref
ms.assetid: 9E9AB3E0-EBDC-4EC3-BFBF-C78EE56BD699
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSBFN_ACTION, USBFN_ACTION, USBFN_ACTION enumeration [Buses], UsbfnActionDetectProprietaryCharger, UsbfnActionNoCad, UsbfnActionNone, _USBFN_ACTION, buses.usbfn_action, ufxbase/USBFN_ACTION, ufxbase/UsbfnActionDetectProprietaryCharger, ufxbase/UsbfnActionNoCad, ufxbase/UsbfnActionNone"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ufxbase.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxbase.h
api_name:
-	USBFN_ACTION
product:
- Windows
targetos: Windows
req.typenames: USBFN_ACTION, *PUSBFN_ACTION
req.product: Windows 10 or later.
---

# _USBFN_ACTION Enumeration
Defines special actions UFX should take when the client driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187963">UfxDevicePortDetectCompleteEx</a> function.

## Syntax
```
typedef enum _USBFN_ACTION {
  UsbfnActionNone                      ,
  UsbfnActionNoCad                     ,
  UsbfnActionDetectProprietaryCharger
} *PUSBFN_ACTION, USBFN_ACTION;
```

## Constants

<table>
            
                <tr>
                    <td>UsbfnActionNone</td>
                    <td>No special action should be taken.</td>
                </tr>
            
                <tr>
                    <td>UsbfnActionNoCad</td>
                    <td>UFX should not notify the battery manager about the detected port type or the maximum current that can be drawn from the upstream port.</td>
                </tr>
            
                <tr>
                    <td>UsbfnActionDetectProprietaryCharger</td>
                    <td>UFX should initiate proprietary charger detection by calling the client driver’s <a href="https://msdn.microsoft.com/library/windows/hardware/mt187850">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback function.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ufxbase.h |