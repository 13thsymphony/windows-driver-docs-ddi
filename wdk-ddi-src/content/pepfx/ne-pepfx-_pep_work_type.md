---
UID: NE:pepfx._PEP_WORK_TYPE
title: "_PEP_WORK_TYPE"
author: windows-driver-content
description: The PEP_WORK_TYPE enumeration describes the type of work that the platform extension plug-in (PEP) is requesting.
old-location: kernel\pep_work_type.htm
old-project: kernel
ms.assetid: 5AED6B9E-5DB8-44AF-925C-4B587D100040
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_WORK_TYPE, PEP_WORK_TYPE, PEP_WORK_TYPE enumeration [Kernel-Mode Driver Architecture], PepWorkAcpiEvaluateControlMethodComplete, PepWorkAcpiNotify, PepWorkActiveComplete, PepWorkCompleteIdleState, PepWorkCompletePerfState, PepWorkDeviceIdle, PepWorkDevicePower, PepWorkMax, PepWorkRequestIdleState, PepWorkRequestPowerControl, _PEP_WORK_TYPE, kernel.pep_work_type, pepfx/PEP_WORK_TYPE, pepfx/PepWorkAcpiEvaluateControlMethodComplete, pepfx/PepWorkAcpiNotify, pepfx/PepWorkActiveComplete, pepfx/PepWorkCompleteIdleState, pepfx/PepWorkCompletePerfState, pepfx/PepWorkDeviceIdle, pepfx/PepWorkDevicePower, pepfx/PepWorkMax, pepfx/PepWorkRequestIdleState, pepfx/PepWorkRequestPowerControl"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_WORK_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# _PEP_WORK_TYPE Enumeration
The <b>PEP_WORK_TYPE</b> enumeration describes the type of work that the platform extension plug-in (PEP) is requesting.

## Syntax
````
typedef enum _PEP_WORK_TYPE { 
  PepWorkActiveComplete,
  PepWorkRequestIdleState,
  PepWorkDevicePower,
  PepWorkRequestPowerControl,
  PepWorkDeviceIdle,
  PepWorkCompleteIdleState,
  PepWorkCompletePerfState,
  PepWorkAcpiNotify,
  PepWorkAcpiEvaluateControlMethodComplete,
  PepWorkMax
} PEP_WORK_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PepWorkRequestPowerControl</td>
                    <td>A request for the device driver to perform a custom power-control operation that uses a device-specific context that the PEP provides for the operation. The driver handles this request in its <a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a> routine.</td>
                </tr>
            
                <tr>
                    <td>PepWorkCompleteIdleState</td>
                    <td>A notification to PoFx that the PEP has asynchronously completed the transition of a component to an idle state. PoFx previously initiated this transition by sending a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186759">PEP_DPM_NOTIFY_COMPONENT_IDLE_STATE</a> notification to the PEP.</td>
                </tr>
            
                <tr>
                    <td>PepWorkCompletePerfState</td>
                    <td>A notification to PoFx that the PEP has asynchronously completed the transition of a component to a P-state. PoFx previously initiated this transition by sending a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186852">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a> notification to the PEP.</td>
                </tr>
            
                <tr>
                    <td>PepWorkAcpiNotify</td>
                    <td>An ACPI Notify code to describe to PoFx a hardware event that the specified device has generated.</td>
                </tr>
            
                <tr>
                    <td>PepWorkAcpiEvaluateControlMethodComplete</td>
                    <td>A notification to PoFx that the PEP has asynchronously finished evaluating an ACPI control method. PoFx previously initiated the evaluation of this method by sending a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186659">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a> notification to the PEP.</td>
                </tr>
            
                <tr>
                    <td>PepWorkMax</td>
                    <td>Reserved for use by operating system.</td>
                </tr>
</table>

## Remarks

This enumeration is used by the <a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a> structure to describe the type of work item that the PEP is requesting.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186852">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186659">PEP_NOTIFY_ACPI_EVALUATE_CONTROL_METHOD</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186759">PEP_DPM_NOTIFY_COMPONENT_IDLE_STATE</a>



<a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a>