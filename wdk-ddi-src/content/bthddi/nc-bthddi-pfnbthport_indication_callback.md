---
UID: NC:bthddi.PFNBTHPORT_INDICATION_CALLBACK
title: PFNBTHPORT_INDICATION_CALLBACK
author: windows-driver-content
description: Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and any changes to the status of a currently open L2CAP connection.
old-location: bltooth\l2cap_callback_function.htm
old-project: bltooth
ms.assetid: d3ca900d-1dd6-49da-ae94-855de3fbd086
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BluetoothPortIndicationCallback, BluetoothPortIndicationCallback callback function [Bluetooth Devices], PFNBTHPORT_INDICATION_CALLBACK, bltooth.l2cap_callback_function, bth_funcs_76d9cb39-ead0-4465-9cc5-83b559b0ba55.xml, bthddi/BluetoothPortIndicationCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	bthddi.h
api_name:
-	BluetoothPortIndicationCallback
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# PFNBTHPORT_INDICATION_CALLBACK callback function
Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a
  mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and
  any changes to the status of a currently open L2CAP connection.

## Syntax

```
PFNBTHPORT_INDICATION_CALLBACK PfnbthportIndicationCallback;

void PfnbthportIndicationCallback(
  IN PVOID Context,
  IN INDICATION_CODE Indication,
  IN PINDICATION_PARAMETERS Parameters
)
{...}
```

## Parameters

`Context`

For incoming remote connection request indications, this is the context specified by the profile
     driver in the 
     <b>IndicationCallbackContext</b> member of the 
     <a href="https://msdn.microsoft.com/b7eca29a-7e3c-4cfc-b285-42faca263c5e">
     _BRB_L2CA_REGISTER_SERVER</a> structure when the profile driver registered the callback function. For
     changes to existing L2CAP connections, this is the 
     <b>CallbackContext</b> member specified by the profile driver when it built and sent a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a> BRB.

`Indication`

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536679">INDICATION_CODE</a> value that indicates the type
     of L2CAP event.

`Parameters`

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a> structure that
     contains event-specific parameters.


## Return Value

None

## Remarks

A profile driver registers its L2CAP callback function in the following two scenarios:

<ol>
<li>
When a profile driver acts as a server, it registers a L2CAP callback function using the 
      <b>IndicationCallback</b> member of the 
      <a href="https://msdn.microsoft.com/b7eca29a-7e3c-4cfc-b285-42faca263c5e">
      _BRB_L2CA_REGISTER_SERVER</a> structure. The Bluetooth driver stack can then notify the profile
      driver when a remote device attempts to contact it.

</li>
<li>
When the profile driver acts as a client and attempts to connect to a remote device using the
      <b>BRB_L2CA_OPEN_CHANNEL</b> BRB, the profile driver registers its L2CAP callback function using the 
      <b>Callback</b> member of the _BRB_L2CA_OPEN_CHANNEL structure that is passed when the profile driver 
      <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">builds and sends</a> a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a> or 
      <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
      BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.

</li>
</ol>
After the profile driver registers its L2CAP callback function, the callback function is only
    associated with the channel that the BRB opened. The Bluetooth driver stack can call the L2CAP callback
    function to notify the profile driver of actions that occur over the open channel to the remote device.
    Profile drivers can register a single callback function to handle channel notifications as a client and
    connection notifications as a server.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a> structure held in
    the 
    <i>Parameters</i> parameter is interpreted according to the value of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536679">INDICATION_CODE</a> enumeration that the Bluetooth
    driver stack passes to the profile driver's L2CAP callback function through the 
    <i>Indication</i> parameter. For most notifications, there is an INDICATION_PARAMETERS union member that
    corresponds to the event and contains event-specific parameters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later.  |
| **Target Platform** | Desktop |
| **Header** | bthddi.h (include Bthddi.h) |
| **IRQL** | Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536679">INDICATION_CODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">_BRB_L2CA_REGISTER_SERVER</a>