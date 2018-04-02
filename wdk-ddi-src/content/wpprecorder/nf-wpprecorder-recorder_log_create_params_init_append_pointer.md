---
UID: NF:wpprecorder.RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
title: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function
author: windows-driver-content
description: The RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER method initializes the RECORDER_LOG_CREATE_PARAMS with the pointer to link logs.
old-location: devtest\recorder_log_create_params_init_append_pointer.htm
old-project: devtest
ms.assetid: EC94E27C-C863-49F0-B13C-B661E96991B7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER, RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function [Driver Development Tools], devtest.recorder_log_create_params_init_append_pointer, wpprecorder/RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wpprecorder.h
api_name:
-	RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---


# RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function
The <b>RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER</b> method initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914608">RECORDER_LOG_CREATE_PARAMS</a> with the pointer to link logs.

## Syntax

```
void RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER(
  PRECORDER_LOG_CREATE_PARAMS Params,
  PSTR                        LogIdentifier,
  PVOID                       LogIdentifierAppendPointer
);
```

## Parameters

`Params`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn914608">RECORDER_LOG_CREATE_PARAMS</a> structure.

`LogIdentifier`

String identifier for the log.

`LogIdentifierAppendPointer`

A pointer from each debug message to its IFR’s metadata structure.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wpprecorder.h |