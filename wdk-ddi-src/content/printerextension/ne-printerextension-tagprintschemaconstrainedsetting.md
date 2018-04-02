---
UID: NE:printerextension.tagPrintSchemaConstrainedSetting
title: tagPrintSchemaConstrainedSetting
author: windows-driver-content
description: The PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The constrained attribute appears only in a PrintCapabilities document.
old-location: print\printschemaconstrainedsetting.htm
old-project: print
ms.assetid: 637A210F-9FD7-49BD-AF71-8A77E07D5C20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PrintSchemaConstrainedSetting, PrintSchemaConstrainedSetting enumeration [Print Devices], PrintSchemaConstrainedSetting_Admin, PrintSchemaConstrainedSetting_Device, PrintSchemaConstrainedSetting_None, PrintSchemaConstrainedSetting_PrintTicket, print.printschemaconstrainedsetting, printerextension/PrintSchemaConstrainedSetting, printerextension/PrintSchemaConstrainedSetting_Admin, printerextension/PrintSchemaConstrainedSetting_Device, printerextension/PrintSchemaConstrainedSetting_None, printerextension/PrintSchemaConstrainedSetting_PrintTicket, tagPrintSchemaConstrainedSetting
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Printerextension.h
api_name:
-	PrintSchemaConstrainedSetting
product: Windows
targetos: Windows
req.typenames: PrintSchemaConstrainedSetting
req.product: Windows 10 or later.
---

# tagPrintSchemaConstrainedSetting Enumeration
The  PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The <b>constrained</b> attribute appears only in a PrintCapabilities document.

## Syntax
```
typedef enum tagPrintSchemaConstrainedSetting {
  PrintSchemaConstrainedSetting_None         ,
  PrintSchemaConstrainedSetting_PrintTicket  ,
  PrintSchemaConstrainedSetting_Admin        ,
  PrintSchemaConstrainedSetting_Device
} PrintSchemaConstrainedSetting;
```

## Constants

<table>
            
                <tr>
                    <td>PrintSchemaConstrainedSetting_None</td>
                    <td>The Option is not constrained.</td>
                </tr>
            
                <tr>
                    <td>PrintSchemaConstrainedSetting_PrintTicket</td>
                    <td>The Option is constrained by the PrintTicket settings. Changing the PrintTicket document settings should be able to remove the constraint.</td>
                </tr>
            
                <tr>
                    <td>PrintSchemaConstrainedSetting_Admin</td>
                    <td>The Option is constrained by the administrator's settings. The Option constraint should not be removable by a user without administrator privileges.</td>
                </tr>
            
                <tr>
                    <td>PrintSchemaConstrainedSetting_Device</td>
                    <td>The Option is constrained by the device configuration. The Option should not be removable by either a user or administrator without changing the device configuration.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/57E13395-9E23-4708-B4EC-6839CB6FC62B">IPrintSchemaOption::Constrained</a>