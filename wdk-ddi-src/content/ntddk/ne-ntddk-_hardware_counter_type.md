---
UID: NE:ntddk._HARDWARE_COUNTER_TYPE
title: "_HARDWARE_COUNTER_TYPE"
author: windows-driver-content
description: The HARDWARE_COUNTER_TYPE enumeration specifies the type of a hardware counter.
old-location: kernel\hardware_counter_type.htm
old-project: kernel
ms.assetid: 837f5a55-ca07-4462-85d7-203d02df168c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/HARDWARE_COUNTER_TYPE, kernel.hardware_counter_type, sysenum_861db9b8-cd2d-4cfe-ae99-5c292f28c420.xml, PMCCounter, MaxHardwareCounterType, ntddk/PHARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE enumeration [Kernel-Mode Driver Architecture], ntddk/MaxHardwareCounterType, PHARDWARE_COUNTER_TYPE, *PHARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE, ntddk/PMCCounter, PHARDWARE_COUNTER_TYPE enumeration pointer [Kernel-Mode Driver Architecture], _HARDWARE_COUNTER_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Winnt.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	HARDWARE_COUNTER_TYPE
product: Windows
targetos: Windows
req.typenames: "*PHARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE"
---

# _HARDWARE_COUNTER_TYPE Enumeration
The <b>HARDWARE_COUNTER_TYPE</b> enumeration specifies the type of a hardware counter.

## Syntax
````
typedef enum _HARDWARE_COUNTER_TYPE { 
  PMCCounter              = 0,
  MaxHardwareCounterType  = 1
} HARDWARE_COUNTER_TYPE, *PHARDWARE_COUNTER_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>MaxHardwareCounterType</td>
                    <td>The maximum value in this enumeration type.</td>
                </tr>
            
                <tr>
                    <td>PMCCounter</td>
                    <td>Performance monitor counter. This type of counter is used by thread-profiling applications.</td>
                </tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="..\ntddk\ns-ntddk-_hardware_counter.md">HARDWARE_COUNTER</a> structure contains a <b>HARDWARE_COUNTER_TYPE</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows 7 and later versions of Windows. Supported in Windows 7 and later versions of Windows. |
| **Header** | ntddk.h (include Winnt.h, Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_hardware_counter.md">HARDWARE_COUNTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HARDWARE_COUNTER_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>