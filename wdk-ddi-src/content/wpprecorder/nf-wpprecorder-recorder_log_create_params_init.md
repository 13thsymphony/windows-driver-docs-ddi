---
UID: NF:wpprecorder.RECORDER_LOG_CREATE_PARAMS_INIT
title: RECORDER_LOG_CREATE_PARAMS_INIT function
author: windows-driver-content
description: The RECORDER_LOG_CREATE_PARAMS_INIT function is used to initialize the RECORDER_LOG_CREATE_PARAMS structure.
old-location: devtest\recorder_log_create_params_init.htm
old-project: devtest
ms.assetid: C91A4DD7-3DDA-4BD9-BA84-233253B72EC7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: RECORDER_LOG_CREATE_PARAMS_INIT, RECORDER_LOG_CREATE_PARAMS_INIT function [Driver Development Tools], devtest.recorder_log_create_params_init, wpprecorder/RECORDER_LOG_CREATE_PARAMS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wpprecorder.h
req.include-header: 
req.target-type: Desktop
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
-	Wpprecorder.h
api_name:
-	RECORDER_LOG_CREATE_PARAMS_INIT
product:
- Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---


# RECORDER_LOG_CREATE_PARAMS_INIT function
The <b>RECORDER_LOG_CREATE_PARAMS_INIT</b> function is used to initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914608">RECORDER_LOG_CREATE_PARAMS</a> structure.

## Syntax

```
void RECORDER_LOG_CREATE_PARAMS_INIT(
  PRECORDER_LOG_CREATE_PARAMS Params,
  PSTR                        LogIdentifier
);
```

## Parameters

`Params`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914608">RECORDER_LOG_CREATE_PARAMS</a> structure to initialize.

`LogIdentifier`




## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wpprecorder.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn914608">RECORDER_LOG_CREATE_PARAMS</a>