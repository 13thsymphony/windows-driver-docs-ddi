---
UID: NE:ntddk._PSCREATETHREADNOTIFYTYPE
title: "_PSCREATETHREADNOTIFYTYPE"
author: windows-driver-content
description: Indicates the type of thread notification. This enumeration is used in PsSetCreateThreadNotifyRoutineEx to register callback notifications associated with thread creation or deletion.
old-location: kernel\pscreatethreadnotifytype.htm
old-project: kernel
ms.assetid: C38F8222-7F22-4D6B-A3F2-C326ECE22E8B
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PSCREATETHREADNOTIFYTYPE, PSCREATETHREADNOTIFYTYPE enumeration [Kernel-Mode Driver Architecture], PsCreateThreadNotifyNonSystem, PsCreateThreadNotifySubsystems, _PSCREATETHREADNOTIFYTYPE, kernel.pscreatethreadnotifytype, ntddk/PSCREATETHREADNOTIFYTYPE, ntddk/PsCreateThreadNotifyNonSystem, ntddk/PsCreateThreadNotifySubsystems
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: Windows Server 2016
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	PSCREATETHREADNOTIFYTYPE
product: Windows
targetos: Windows
req.typenames: PSCREATETHREADNOTIFYTYPE
---

# _PSCREATETHREADNOTIFYTYPE Enumeration
Indicates the type of thread notification. This enumeration is used in <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutineex.md">PsSetCreateThreadNotifyRoutineEx</a> to register callback notifications associated with thread creation or deletion.

## Syntax
````
typedef enum _PSCREATETHREADNOTIFYTYPE { 
  PsCreateThreadNotifyNonSystem   = 0,
  PsCreateThreadNotifySubsystems  = 1
} PSCREATETHREADNOTIFYTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PsCreateThreadNotifyNonSystem</td>
                    <td>The driver-registered callback function is executed on the new non-system thread, which enables the callback function to perform tasks such as setting the initial thread context.</td>
                </tr>
            
                <tr>
                    <td>PsCreateThreadNotifySubsystems</td>
                    <td>Indicates that the driver-registered callback function is invoked for threads of all subsystems.  Drivers can call <a href="https://msdn.microsoft.com/ca292efc-1ea9-4c0f-b0a7-1cfb35d69f81">NtQueryInformationThread</a> to determine the underlying subsystem. The query retrieves a  <a href="..\ntddk\ne-ntddk-_subsystem_information_type.md">SUBSYSTEM_INFORMATION_TYPE</a> value.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1703 Windows 10, version 1703 |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ne-ntddk-_subsystem_information_type.md">SUBSYSTEM_INFORMATION_TYPE</a>



<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutineex.md">PsSetCreateThreadNotifyRoutineEx</a>



<a href="https://msdn.microsoft.com/ca292efc-1ea9-4c0f-b0a7-1cfb35d69f81">NtQueryInformationThread</a>