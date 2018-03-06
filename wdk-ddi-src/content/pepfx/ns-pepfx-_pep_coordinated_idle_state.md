---
UID: NS:pepfx._PEP_COORDINATED_IDLE_STATE
title: "_PEP_COORDINATED_IDLE_STATE"
author: windows-driver-content
description: The PEP_COORIDNATED_IDLE_STATE structure describes a coordinated idle state to the OS.
old-location: kernel\pep_coordinated_idle_state.htm
old-project: kernel
ms.assetid: 0B3B53F8-2D1E-430B-9C51-E35465899811
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_COORDINATED_IDLE_STATE, PEP_COORDINATED_IDLE_STATE, PEP_COORDINATED_IDLE_STATE structure [Kernel-Mode Driver Architecture], PPEP_COORDINATED_IDLE_STATE, PPEP_COORDINATED_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_COORDINATED_IDLE_STATE, kernel.pep_coordinated_idle_state, pepfx/PEP_COORDINATED_IDLE_STATE, pepfx/PPEP_COORDINATED_IDLE_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pepfx.h
api_name:
-	PEP_COORDINATED_IDLE_STATE
product: Windows
targetos: Windows
req.typenames: PEP_COORDINATED_IDLE_STATE, *PPEP_COORDINATED_IDLE_STATE
---

# _PEP_COORDINATED_IDLE_STATE structure
The <b>PEP_COORIDNATED_IDLE_STATE</b> structure describes a coordinated idle state to the OS.

## Syntax
````
typedef struct _PEP_COORDINATED_IDLE_STATE {
  ULONG Latency;
  ULONG BreakEvenDuration;
  ULONG DependencyCount;
  ULONG MaximumDependencySize;
} PEP_COORDINATED_IDLE_STATE, *PPEP_COORDINATED_IDLE_STATE;
````

## Members


`BreakEvenDuration`

Supplies the minimum time the state must be entered to amortize the cost of entering/exiting the state. Idle durations longer than this period should save power when compared to entering a lighter state for the same period.

`DependencyCount`

Supplies the number of dependencies this coordinated state has on other coordinated states or on processors.

`Latency`

The latency of waking from this idle state, in 100ns units.

`MaximumDependencySize`

Supplies the maximum size of a single dependency.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_coordinated_idle_state.md">PEP_COORDINATED_IDLE_STATE structure</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186776">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COORDINATED_IDLE_STATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>