---
UID: NE.ufxbase._USBFN_ACTION
title: _USBFN_ACTION
author: windows-driver-content
description: Defines special actions UFX should take when the client driver calls the UfxDevicePortDetectCompleteEx function.
old-location: buses\usbfn_action.htm
old-project: UsbRef
ms.assetid: 9E9AB3E0-EBDC-4EC3-BFBF-C78EE56BD699
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USBFN_ACTION, PUSBFN_ACTION, *PUSBFN_ACTION, USBFN_ACTION
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
req.alt-api: USBFN_ACTION
req.alt-loc: ufxbase.h
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
req.product: Windows 10 or later.
---

# _USBFN_ACTION enumeration



## -description
Defines special actions UFX should take when the client driver calls the <a href="buses.ufxdeviceportdetectcompleteex">UfxDevicePortDetectCompleteEx</a> function.



## -syntax

````
typedef enum _USBFN_ACTION { 
  UsbfnActionNone                      = 0,
  UsbfnActionNoCad,
  UsbfnActionDetectProprietaryCharger
} USBFN_ACTION;
````


## -enum-fields

### -field UsbfnActionNone

No special action should be taken.


### -field UsbfnActionNoCad

UFX should not notify the battery manager about the detected port type or the maximum current that can be drawn from the upstream port.


### -field UsbfnActionDetectProprietaryCharger

UFX should initiate proprietary charger detection by calling the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_detect.md">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback function.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufxbase.h</dt>
</dl>
</td>
</tr>
</table>