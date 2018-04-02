---
UID: NS:ntpoapi._SYSTEM_POWER_STATE_CONTEXT
title: "_SYSTEM_POWER_STATE_CONTEXT"
author: windows-driver-content
description: The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer.
old-location: kernel\system_power_state_context.htm
old-project: kernel
ms.assetid: C924C7BD-071C-4A98-9A9B-2BEFA1101DF3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PSYSTEM_POWER_STATE_CONTEXT, PSYSTEM_POWER_STATE_CONTEXT, PSYSTEM_POWER_STATE_CONTEXT structure pointer [Kernel-Mode Driver Architecture], SYSTEM_POWER_STATE_CONTEXT, SYSTEM_POWER_STATE_CONTEXT structure [Kernel-Mode Driver Architecture], _SYSTEM_POWER_STATE_CONTEXT, kernel.system_power_state_context, wdm/PSYSTEM_POWER_STATE_CONTEXT, wdm/SYSTEM_POWER_STATE_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntpoapi.h
req.include-header: Ntpoapi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	Wdm.h
api_name:
-	SYSTEM_POWER_STATE_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---

# _SYSTEM_POWER_STATE_CONTEXT structure
The <b>SYSTEM_POWER_STATE_CONTEXT</b> structure is a partially opaque system structure that contains information about the previous system power states of a computer.

## Syntax
```
typedef struct _SYSTEM_POWER_STATE_CONTEXT {
  union {
    ULONG ContextAsUlong;
    struct {
      ULONG  : 8 Reserved1;
      ULONG  : 4 TargetSystemState;
      ULONG  : 4 EffectiveSystemState;
      ULONG  : 4 CurrentSystemState;
      ULONG  : 1 IgnoreHibernationPath;
      ULONG  : 1 PseudoTransition;
      ULONG  : 1 KernelSoftReboot;
      ULONG  : 9 Reserved2;
    } DUMMYSTRUCTNAME;
  } DUMMYUNIONNAME;
} *PSYSTEM_POWER_STATE_CONTEXT, SYSTEM_POWER_STATE_CONTEXT;
```

## Members


`DUMMYUNIONNAME`

Unnamed union.



#### ContextAsUlong

Opaque member. Reserved for system use.

## Remarks
Starting with Windows Vista, the <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> in a <a href="https://msdn.microsoft.com/a37e8dda-af7a-4f28-bf04-908a74bb5b2f">system power IRP</a> contains a <b>SYSTEM_POWER_STATE_CONTEXT</b> structure. The <b>Power</b> member of the <b>IO_STACK_LOCATION</b> structure contains a <b>SystemPowerStateContext</b> member, which is a <b>SYSTEM_POWER_STATE_CONTEXT</b> structure. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>.

The size of the <b>SYSTEM_POWER_STATE_CONTEXT</b> structure is four bytes. This structure is divided into bit fields, most of which are opaque to drivers and reserved exclusively for use by the operating system. However, two of these bit fields, <b>TargetSystemState</b> and <b>EffectiveSystemState</b>, can be read by kernel-mode drivers to distinguish a fast startup from a wake-from-hibernation startup. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj835779">Distinguishing Fast Startup from Wake-from-Hibernation</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | ntpoapi.h (include Ntpoapi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>