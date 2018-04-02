---
UID: NS:winddiui._DRIVER_UPGRADE_INFO_2
title: "_DRIVER_UPGRADE_INFO_2"
author: windows-driver-content
description: The DRIVER_UPGRADE_INFO_2 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function.
old-location: print\driver_upgrade_info_2.htm
old-project: print
ms.assetid: 691554c5-5c99-40f0-b0d6-3556e004dd30
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDRIVER_UPGRADE_INFO_2, DRIVER_UPGRADE_INFO_2, DRIVER_UPGRADE_INFO_2 structure [Print Devices], PDRIVER_UPGRADE_INFO_2, PDRIVER_UPGRADE_INFO_2 structure pointer [Print Devices], _DRIVER_UPGRADE_INFO_2, print.driver_upgrade_info_2, print_interface-graphics_3db7d8d4-1f0c-4b76-9e22-bc55aac9b6c7.xml, winddiui/DRIVER_UPGRADE_INFO_2, winddiui/PDRIVER_UPGRADE_INFO_2"
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
-	DRIVER_UPGRADE_INFO_2
product:
- Windows
targetos: Windows
req.typenames: DRIVER_UPGRADE_INFO_2, *PDRIVER_UPGRADE_INFO_2
req.product: Windows 10 or later.
---

# _DRIVER_UPGRADE_INFO_2 structure
The DRIVER_UPGRADE_INFO_2 structure is used as an input to a printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548648">DrvUpgradePrinter</a> function.

## Syntax
```
typedef struct _DRIVER_UPGRADE_INFO_2 {
  LPTSTR pPrinterName;
  LPTSTR pOldDriverDirectory;
  DWORD  cVersion;
  LPTSTR pName;
  LPTSTR pEnvironment;
  LPTSTR pDriverPath;
  LPTSTR pDataFile;
  LPTSTR pConfigFile;
  LPTSTR pHelpFile;
  LPTSTR pDependentFiles;
  LPTSTR pMonitorName;
  LPTSTR pDefaultDataType;
  LPTSTR pszzPreviousNames;
} *PDRIVER_UPGRADE_INFO_2, DRIVER_UPGRADE_INFO_2;
```

## Members


`pPrinterName`

Pointer to a NULL-terminated string that specifies the name of the printer. For more information, see the Remarks section.

`pOldDriverDirectory`

Pointer to a NULL-terminated string that specifies the local directory in which the old printer driver files can be found.

`cVersion`

Specifies the operating system version for which the driver was written. 

<table>
<tr>
<th>Value</th>
<th>Operating System</th>
</tr>
<tr>
<td>
0

</td>
<td>
Windows 95/98/Me

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Windows NT 3.1 through Windows NT 3.51

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Windows NT 4.0

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Windows 2000 and later

</td>
</tr>
</table>

`pName`

Pointer to a NULL-terminated string that specifies the name of the driver (for example, "QMS 810"). For more information, see the Remarks section.

`pEnvironment`

Pointer to a NULL-terminated string that specifies the environment for which the driver was written (for example, "Windows NT x86" or "Windows Itanium").

`pDriverPath`

Pointer to a NULL-terminated string that specifies a file name or full path and file name for the file that contains the device driver (for example, "pscript.dll").

`pDataFile`

Pointer to a NULL-terminated string that specifies a file name or a full path and file name for the file that contains driver data (for example, "qms810.ppd").

`pConfigFile`

Pointer to a NULL-terminated string that specifies a file name or a full path and file name for the device driver's configuration dynamic-link library (for example, "pscrptui.dll").

`pHelpFile`

Pointer to a null-terminated string that specifies a file name or a full path and file name for the device driver's help file.

`pDependentFiles`

Pointer to a NULL-terminated string that specifies the files the driver depends on. Each file name in the string is also terminated with a null character (for example, "pscript.dll\0qms810.ppd\0pscrptui.dll\0pscrptui.hlp\0pstest.txt\0\0").

`pMonitorName`

Pointer to a NULL-terminated string that specifies a language monitor (for example, "PJL monitor"). This member can be <b>NULL</b> and should be specified as non-<b>NULL</b> only for printers capable of bidirectional communication.

`pDefaultDataType`

Pointer to a NULL-terminated string that specifies the default data type of the print job (for example, "EMF").

`pszzPreviousNames`

Pointer to a NULL-terminated string that specifies any previous printer driver names that are compatible with this driver (for example, "OldName1\0OldName2\0\0").

## Remarks
When DrvUpgradePrinter is called with its <i>pDriverUpgradeInfo</i> parameter pointing to a DRIVER_UPGRADE_INFO_2 structure, the <b>pPrinterName</b> member points to a string containing the name of the printer to be updated. The <b>pName</b> member points to a string containing the name of the printer driver to be updated, which is not necessarily the driver for the printer whose name is pointed to by the <b>pPrinterName</b> member. 

To see how this can occur, suppose that a computer is connected to two printers, one whose driver is named "Acme Plotter" and the other whose driver is named "Acme RasterMaster". Suppose also that both drivers share a common driver file, plotui.dll. When the "Acme Plotter" driver is updated by a call to the <b>AddPrinterDriverEx</b> function (described in the Microsoft Windows SDK documentation), DrvUpgradePrinter is called for both printers, because both drivers use files affected by the upgrade. In both calls, the <b>pName</b> member points to "Acme Plotter", the name of the printer driver used in the call to <b>AddPrinterDriverEx</b>. The string pointed to by the <b>pPrinterName</b> member is different in both calls to DrvUpgradePrinter, however. In each call, <b>pPrinterName</b> points to the name of the printer being updated.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winddiui.h (include Winddiui.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548522">DRIVER_UPGRADE_INFO_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548648">DrvUpgradePrinter</a>