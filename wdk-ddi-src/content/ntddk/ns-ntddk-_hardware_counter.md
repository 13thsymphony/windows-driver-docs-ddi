---
UID: NS:ntddk._HARDWARE_COUNTER
title: "_HARDWARE_COUNTER"
author: windows-driver-content
description: The HARDWARE_COUNTER structure contains information about a hardware counter.
old-location: kernel\hardware_counter.htm
old-project: kernel
ms.assetid: 15eeeb07-b71f-4868-8854-6a5034d3f8c6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/HARDWARE_COUNTER, kstruct_b_3e230097-13da-4e6b-bb89-baf3563c3570.xml, _HARDWARE_COUNTER, kernel.hardware_counter, HARDWARE_COUNTER structure [Kernel-Mode Driver Architecture], HARDWARE_COUNTER, ntddk/PHARDWARE_COUNTER, *PHARDWARE_COUNTER, PHARDWARE_COUNTER, PHARDWARE_COUNTER structure pointer [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	HARDWARE_COUNTER
product: Windows
targetos: Windows
req.typenames: HARDWARE_COUNTER, *PHARDWARE_COUNTER
---

# _HARDWARE_COUNTER structure
The <b>HARDWARE_COUNTER</b> structure contains information about a hardware counter.

## Syntax
````
typedef struct _HARDWARE_COUNTER {
  HARDWARE_COUNTER_TYPE Type;
  ULONG                 Reserved;
  ULONG64               Index;
} HARDWARE_COUNTER, *PHARDWARE_COUNTER;
````

## Members


`Index`

Specifies the hardware counter index. Each hardware counter in a performance monitoring unit (PMU) for a processor is identified by an index.

`Reserved`

Reserved for use by the operating system. Initialize this member to zero.

`Type`

Specifies the type of the hardware counter. Set this member to the following <a href="..\ntddk\ne-ntddk-_hardware_counter_type.md">HARDWARE_COUNTER_TYPE</a> enumeration value:
<ul>
<li>
<b>PMCCounter</b>

</li>
</ul>

## Remarks
This structure is used by the <a href="..\ntddk\nf-ntddk-kequeryhardwarecounterconfiguration.md">KeQueryHardwareCounterConfiguration</a> and <a href="..\ntddk\nf-ntddk-kesethardwarecounterconfiguration.md">KeSetHardwareCounterConfiguration</a> routines. 

The <b>Type</b> member specifies the type of hardware counter that is described by the structure. In Windows 7, the only defined hardware counter type is <b>PMCCounter</b>, which is a performance monitor counter. This type of counter is used by thread-profiling applications.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows 7 and later versions of Windows. Supported in Windows 7 and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ne-ntddk-_hardware_counter_type.md">HARDWARE_COUNTER_TYPE</a>

<a href="..\ntddk\nf-ntddk-kesethardwarecounterconfiguration.md">KeSetHardwareCounterConfiguration</a>

<a href="..\ntddk\nf-ntddk-kequeryhardwarecounterconfiguration.md">KeQueryHardwareCounterConfiguration</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HARDWARE_COUNTER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>