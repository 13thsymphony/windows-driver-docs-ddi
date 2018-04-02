---
UID: NS:pepfx._PEP_WORK_INFORMATION
title: "_PEP_WORK_INFORMATION"
author: windows-driver-content
description: The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx).
old-location: kernel\pep_work_information.htm
old-project: kernel
ms.assetid: 7A3B2A94-AE6F-4DCC-9CDF-E2D5799C9F0D
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_WORK_INFORMATION, PEP_WORK_INFORMATION, PEP_WORK_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_WORK_INFORMATION, PPEP_WORK_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_INFORMATION, kernel.pep_work_information, pepfx/PEP_WORK_INFORMATION, pepfx/PPEP_WORK_INFORMATION"
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
-	PEP_WORK_INFORMATION
product: Windows
targetos: Windows
req.typenames: PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION
---

# _PEP_WORK_INFORMATION structure
The <b>PEP_WORK_INFORMATION</b> structure describes a work item that the PEP is submitting to the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).

## Syntax
```
typedef struct _PEP_WORK_INFORMATION {
  PEP_WORK_TYPE WorkType;
  union {
    PEP_WORK_ACPI_NOTIFY                           AcpiNotify;
    PEP_WORK_COMPLETE_IDLE_STATE                   CompleteIdleState;
    PEP_WORK_COMPLETE_PERF_STATE                   CompletePerfState;
    PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE ControlMethodComplete;
    PEP_WORK_POWER_CONTROL                         PowerControl;
  };
} PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION;
```

## Members


`WorkType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186866">PEP_WORK_TYPE</a> enumeration value. This member indicates the type of work requested by the PEP, which also determines the type of structure that is contained in the unnamed union in the <b>PEP_WORK_INFORMATION</b> structure.

## Remarks
The <b>WorkInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186859">PEP_WORK</a> structure is a pointer to a <b>PEP_WORK_INFORMATION</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186859">PEP_WORK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186861">PEP_WORK_ACPI_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629128">PEP_WORK_ACTIVE_COMPLETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186862">PEP_WORK_COMPLETE_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186863">PEP_WORK_COMPLETE_PERF_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629129">PEP_WORK_DEVICE_IDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629130">PEP_WORK_DEVICE_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629131">PEP_WORK_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186865">PEP_WORK_POWER_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186866">PEP_WORK_TYPE</a>