---
UID: NF:iddcx.IddCxMonitorSetupHardwareCursor
title: IddCxMonitorSetupHardwareCursor function
author: windows-driver-content
description: An OS callback function the driver calls when it wants to setup hardware cursor support for the path.
old-location: display\iddcxmonitorsetuphardwarecursor.htm
old-project: display
ms.assetid: 6182898d-d7c0-4ff2-b222-d83bd00cd1ec
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IddCxMonitorSetupHardwareCursor, IddCxMonitorSetupHardwareCursor method [Display Devices], display.iddcxmonitorsetuphardwarecursor, iddcx/IddCxMonitorSetupHardwareCursor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: "_Must_inspect_result_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IddCxMonitorSetupHardwareCursor
product: Windows
targetos: Windows
req.typenames: 
---


# IddCxMonitorSetupHardwareCursor function
An OS callback function the driver calls when it wants to setup hardware cursor support for the path.  By default when a mode is committed on a path software cursor is enabled, if the driver wants to accelerate the cursor on that path it uses this callback to enable hardware cursor support.

## Syntax

```
NTSTATUS IddCxMonitorSetupHardwareCursor(
  IDDCX_MONITOR                 MonitorObject,
  CONST IDARG_IN_SETUP_HWCURSOR *pInArgs
);
```

## Parameters

`MonitorObject`

The handle the OS provided to identify the monitor

`pInArgs`

Input arguments of function


## Return Value

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | iddcx.h |
| **IRQL** | "_Must_inspect_result_" |