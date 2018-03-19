---
UID: NS:pepfx._PEP_WORK
title: "_PEP_WORK"
author: windows-driver-content
description: The PEP_WORK structure indicates whether the PEP has a work request to submit to the Windows power management framework (PoFx).
old-location: kernel\pep_work.htm
old-project: kernel
ms.assetid: 7C6ACFDD-809E-4E75-8E4D-8A4E0207593E
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_WORK, PEP_WORK, PEP_WORK structure [Kernel-Mode Driver Architecture], PPEP_WORK, PPEP_WORK structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK, kernel.pep_work, pepfx/PEP_WORK, pepfx/PPEP_WORK"
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
-	PEP_WORK
product: Windows
targetos: Windows
req.typenames: PEP_WORK, *PPEP_WORK
---

# _PEP_WORK structure
The <b>PEP_WORK</b> structure indicates whether the PEP has a work request to submit to the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).

## Syntax
````
typedef struct _PEP_WORK {
  PPEP_WORK_INFORMATION WorkInformation;
  BOOLEAN               NeedWork;
} PEP_WORK, *PPEP_WORK;
````

## Members


`WorkInformation`

[out] A pointer to a PEP-allocated <a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a> structure that describes the work that the PEP is requesting. If <b>NeedWork</b> is TRUE, <b>WorkInformation</b> must point to a valid <b>PEP_WORK_INFORMATION</b> structure. If <b>NeedWork</b> is FALSE, <b>WorkInformation</b> must be NULL.

`NeedWork`

[out] Whether the PEP has a work request to submit. Set this member to TRUE if the PEP has a work request, or to FALSE if the PEP has no work to request.

## Remarks
This structure is used by the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification. Both members of the structure contain values that the PEP writes to the structure in response to this notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>