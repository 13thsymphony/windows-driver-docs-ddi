---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_TIME
title: PUSB_BUSIFFN_QUERY_BUS_TIME
author: windows-driver-content
description: The QueryBusTime function gets the current 32-bit USB frame number.
old-location: buses\querybustime.htm
old-project: usbref
ms.assetid: 6a0a1953-070d-4335-a906-4ca3fe8a04e1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_TIME, QueryBusTime, QueryBusTime callback function [Buses], USB_BUSIFFN_QUERY_BUS_TIME, buses.querybustime, usbbusif/QueryBusTime, usbinterKR_857e67cf-8b61-43e3-b07f-25968e2672d4.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
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
req.irql: "< = DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	QueryBusTime
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---


# PUSB_BUSIFFN_QUERY_BUS_TIME callback function
The <i>QueryBusTime</i> function gets the current 32-bit USB frame number.

## Syntax

```
PUSB_BUSIFFN_QUERY_BUS_TIME PusbBusiffnQueryBusTime;

NTSTATUS PusbBusiffnQueryBusTime(
  PVOID ,
  PULONG 
)
{...}
```

## Parameters

`Arg1`



`Arg1`




## Return Value

Returns STATUS_SUCCESS on success, and the appropriate error code on failure.

## Remarks

This routine replaces the <b>USBD_QueryBusTime</b>  library function provided by usbd.sys. 

The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_TIME) (
    IN PVOID,
    IN PULONG</code></pre>
  );

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbbusif.h (include Usbbusif.h) |
| **IRQL** | "< = DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539210">USB_BUS_INTERFACE_USBDI_V0</a>