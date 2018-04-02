---
UID: NS:winddiui._DRIVER_UPGRADE_INFO_1
title: "_DRIVER_UPGRADE_INFO_1"
author: windows-driver-content
description: The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function.
old-location: print\driver_upgrade_info_1.htm
old-project: print
ms.assetid: fef7c63b-ca9e-47f4-96cb-4dafa080ddcf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDRIVER_UPGRADE_INFO_1, DRIVER_UPGRADE_INFO_1, DRIVER_UPGRADE_INFO_1 structure [Print Devices], PDRIVER_UPGRADE_INFO_1, PDRIVER_UPGRADE_INFO_1 structure pointer [Print Devices], _DRIVER_UPGRADE_INFO_1, print.driver_upgrade_info_1, print_interface-graphics_eb7333cb-f073-4c0b-ade4-20a477d28f67.xml, winddiui/DRIVER_UPGRADE_INFO_1, winddiui/PDRIVER_UPGRADE_INFO_1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winddiui.h
api_name:
-	DRIVER_UPGRADE_INFO_1
product:
- Windows
targetos: Windows
req.typenames: DRIVER_UPGRADE_INFO_1, *PDRIVER_UPGRADE_INFO_1
req.product: Windows 10 or later.
---

# _DRIVER_UPGRADE_INFO_1 structure
The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548648">DrvUpgradePrinter</a> function.

## Syntax
```
typedef struct _DRIVER_UPGRADE_INFO_1 {
  LPTSTR pPrinterName;
  LPTSTR pOldDriverDirectory;
} *PDRIVER_UPGRADE_INFO_1, DRIVER_UPGRADE_INFO_1;
```

## Members


`pPrinterName`

Pointer to a NULL-terminated string that specifies the name of the printer.

`pOldDriverDirectory`

Pointer to a NULL-terminated string that specifies the local directory in which the old printer driver files can be found.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winddiui.h (include Winddiui.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548527">DRIVER_UPGRADE_INFO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548648">DrvUpgradePrinter</a>