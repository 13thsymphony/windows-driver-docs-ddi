---
UID: NC:gpioclx.GPIO_CLIENT_CONNECT_IO_PINS
title: GPIO_CLIENT_CONNECT_IO_PINS
author: windows-driver-content
description: The CLIENT_ConnectIoPins event callback function opens a logical connection to a set of general-purpose I/O (GPIO) pins and configures these pins for data read or write operations.
old-location: gpio\client_connectiopins.htm
old-project: GPIO
ms.assetid: 9DE89026-872C-4537-BD99-131320B3C258
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_connectiopins, CLIENT_ConnectIoPins callback function [Parallel Ports], CLIENT_ConnectIoPins, GPIO_CLIENT_CONNECT_IO_PINS, GPIO_CLIENT_CONNECT_IO_PINS, gpioclx/CLIENT_ConnectIoPins
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_ConnectIoPins
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---


# GPIO_CLIENT_CONNECT_IO_PINS function
The <i>CLIENT_ConnectIoPins</i> event callback function opens a logical connection to a set of general-purpose I/O (GPIO) pins and configures these pins for data read or write operations.

## Syntax

```
GPIO_CLIENT_CONNECT_IO_PINS GpioClientConnectIoPins;

NTSTATUS GpioClientConnectIoPins(
  PVOID Context,
  PGPIO_CONNECT_IO_PINS_PARAMETERS ConnectParameters
)
{...}
```

## Parameters

`Context`

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.

`ConnectParameters`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439502">GPIO_CONNECT_IO_PINS_PARAMETERS</a> structure that describes a connection to a set of GPIO pins and that specifies whether to configure these pins as data inputs or outputs.


## Return Value

The <i>CLIENT_ConnectIoPins</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to open a connection to a set of GPIO pins. These pins are specified in the <b>PinNumberTable</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439502">GPIO_CONNECT_IO_PINS_PARAMETERS</a> structure pointed to by <i>ConnectParameters</i>. The <b>ConnectMode</b> member of this structure indicates whether to configure the pins as inputs or outputs.

To close the connection, GpioClx calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439374">CLIENT_DisconnectIoPins</a> callback function.

To register your driver's <i>CLIENT_ConnectIoPins</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_ConnectIoPins</i> function pointer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | gpioclx.h |
| **IRQL** | Called at PASSIVE_LEVEL. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439374">CLIENT_DisconnectIoPins</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ConnectIoPins callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>