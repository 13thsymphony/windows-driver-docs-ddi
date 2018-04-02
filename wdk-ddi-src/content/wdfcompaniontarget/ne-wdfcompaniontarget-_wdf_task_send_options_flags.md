---
UID: NE:wdfcompaniontarget._WDF_TASK_SEND_OPTIONS_FLAGS
title: "_WDF_TASK_SEND_OPTIONS_FLAGS"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_send_options_flags.htm
old-project: wdf
ms.assetid: 8ff13908-57f2-404f-a8ea-70c798ee3d7d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_TASK_SEND_OPTIONS_FLAGS, WDF_TASK_SEND_OPTIONS_FLAGS enumeration, WDF_TASK_SEND_OPTION_SYNCHRONOUS, WDF_TASK_SEND_OPTION_TIMEOUT, _WDF_TASK_SEND_OPTIONS_FLAGS, wdf.wdf_task_send_options_flags, wdfcompaniontarget/WDF_TASK_SEND_OPTIONS_FLAGS, wdfcompaniontarget/WDF_TASK_SEND_OPTION_SYNCHRONOUS, wdfcompaniontarget/WDF_TASK_SEND_OPTION_TIMEOUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfcompaniontarget.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
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
-	wdfcompaniontarget.h
api_name:
-	WDF_TASK_SEND_OPTIONS_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_TASK_SEND_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# _WDF_TASK_SEND_OPTIONS_FLAGS Enumeration
For internal use only.

## Syntax
```
typedef enum _WDF_TASK_SEND_OPTIONS_FLAGS {
  WDF_TASK_SEND_OPTION_TIMEOUT      ,
  WDF_TASK_SEND_OPTION_SYNCHRONOUS
} WDF_TASK_SEND_OPTIONS_FLAGS;
```

## Constants

<table>
            
                <tr>
                    <td>WDF_TASK_SEND_OPTION_TIMEOUT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WDF_TASK_SEND_OPTION_SYNCHRONOUS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.23 |
| **Header** | wdfcompaniontarget.h |