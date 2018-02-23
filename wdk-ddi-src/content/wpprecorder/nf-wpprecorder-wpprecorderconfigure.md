---
UID: NF:wpprecorder.WppRecorderConfigure
title: WppRecorderConfigure macro
author: windows-driver-content
description: The WppRecorderConfigure method enables or disables the default log to which WPP prints.
old-location: devtest\wpprecorderconfigure.htm
old-project: devtest
ms.assetid: 995E4606-F987-46A7-8310-28E8E9C7682C
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: imp_WppRecorderConfigure, devtest.wpprecorderconfigure, WppRecorderConfigure, imp_WppRecorderConfigure function [Driver Development Tools], wpprecorder/imp_WppRecorderConfigure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wpprecorder.h
req.include-header: 
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
req.lib: wpprecorder.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wpprecorder.h
apiname:
-	imp_WppRecorderConfigure
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# WppRecorderConfigure function
The <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderconfigure.md">WppRecorderConfigure</a> method enables or disables the default log to which WPP prints.

## Syntax

````
NTSTATUS imp_WppRecorderConfigure(
   PRECORDER_CONFIGURE_PARAMS ConfigureParams
);
````

## Parameters

`ConfigureParams`

Pointer to a caller-allocated RECORDER_CONFIGURE_PARAMS structure.


## Return Value

None

## Remarks

Before calling <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderconfigure.md">WppRecorderConfigure</a>, allocate a <a href="..\wpprecorder\ns-wpprecorder-_recorder_configure_params.md">RECORDER_CONFIGURE_PARAMS</a> structure and initialize by calling <a href="..\wpprecorder\nf-wpprecorder-recorder_configure_params_init.md">RECORDER_CONFIGURE_PARAMS_INIT</a>. 

This method only configures the default log. By default that log is enabled. If you have a custom log, you must disable the default log by setting the <b>CreateDefaultLog</b> to FALSE.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wpprecorder.h |
| **Library** | wpprecorder.h |