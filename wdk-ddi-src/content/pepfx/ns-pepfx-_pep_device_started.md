---
UID: NS:pepfx._PEP_DEVICE_STARTED
title: "_PEP_DEVICE_STARTED"
author: windows-driver-content
description: The PEP_DEVICE_STARTED structure identifies a device whose driver has completed its registration with the Windows power management framework (PoFx).
old-location: kernel\pep_device_started.htm
old-project: kernel
ms.assetid: 02A30A9F-A27D-492E-8FB3-D8CB34D51D5A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_DEVICE_STARTED, PEP_DEVICE_STARTED, PEP_DEVICE_STARTED structure [Kernel-Mode Driver Architecture], PPEP_DEVICE_STARTED, PPEP_DEVICE_STARTED structure pointer [Kernel-Mode Driver Architecture], _PEP_DEVICE_STARTED, kernel.pep_device_started, pepfx/PEP_DEVICE_STARTED, pepfx/PPEP_DEVICE_STARTED"
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
-	PEP_DEVICE_STARTED
product: Windows
targetos: Windows
req.typenames: PEP_DEVICE_STARTED, *PPEP_DEVICE_STARTED
---

# _PEP_DEVICE_STARTED structure
The <b>PEP_DEVICE_STARTED</b> structure identifies a device whose driver has completed its registration with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

## Syntax
```
typedef struct _PEP_DEVICE_STARTED {
  PEPHANDLE DeviceHandle;
} *PPEP_DEVICE_STARTED, PEP_DEVICE_STARTED;
```

## Members


`DeviceHandle`

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186714">PEP_DPM_DEVICE_STARTED</a> notification. The <b>DeviceHandle</b> member of this structure contains an input value that is supplied by PoFx.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186714">PEP_DPM_DEVICE_STARTED</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>