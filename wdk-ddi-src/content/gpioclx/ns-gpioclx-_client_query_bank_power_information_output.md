---
UID: NS:gpioclx._CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
title: "_CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT"
author: windows-driver-content
description: The CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_query_bank_power_information_output.htm
old-project: GPIO
ms.assetid: 156115CB-FF0C-4E53-BB7E-CF98420DF443
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gpioclx/PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, GPIO.client_query_bank_power_information_output, gpioclx/CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure pointer [Parallel Ports], CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure [Parallel Ports], *PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
product: Windows
targetos: Windows
req.typenames: "*PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT"
---

# _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure
The <b>CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</b> structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.

## Syntax
````
typedef struct _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT {
  struct {
    USHORT F1StateSupported  :1;
    USHORT Reserved  :15;
  };
  PO_FX_COMPONENT_IDLE_STATE F1IdleStateParameters;
} CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, *PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT;
````

## Members


`F1IdleStateParameters`

A <b>PO_FX_COMPONENT_IDLE_STATE</b> structure that describes the parameters (transition latency, residency requirement, and so on) for the F1 power state of the GPIO bank. For more information about these parameters, see <a href="..\wdm\ns-wdm-_po_fx_component_idle_state.md">PO_FX_COMPONENT_IDLE_STATE</a>.

## Remarks
The <b>BankPowerInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure is a structure of type <b>CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</b>.

For more information about GPIO banks, see <a href="https://msdn.microsoft.com/D9425459-E052-48D8-A4F3-91387AE7059A">Partioning a GPIO Controller into Banks of Pins</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | gpioclx.h |

## See Also

<a href="..\wdm\ns-wdm-_po_fx_component_idle_state.md">PO_FX_COMPONENT_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>