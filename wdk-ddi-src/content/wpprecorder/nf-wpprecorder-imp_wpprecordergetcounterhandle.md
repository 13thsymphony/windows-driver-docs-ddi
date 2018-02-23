---
UID: NF:wpprecorder.imp_WppRecorderGetCounterHandle
title: imp_WppRecorderGetCounterHandle function
author: windows-driver-content
description: The WppRecorderGetCounterHandle method.
old-location: devtest\wpprecordergetcounterhandle.htm
old-project: devtest
ms.assetid: 389A4F90-9C81-4C03-A2F9-ACF0E597018C
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WppRecorderGetCounterHandle, devtest.wpprecordergetcounterhandle, imp_WppRecorderGetCounterHandle function [Driver Development Tools], imp_WppRecorderGetCounterHandle, wpprecorder/imp_WppRecorderGetCounterHandle
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wpprecorder.h
apiname:
-	imp_WppRecorderGetCounterHandle
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# imp_WppRecorderGetCounterHandle function
The <b>WppRecorderGetCounterHandle</b> method gets the ID of the counter whose current value is to be read.

## Syntax

````
WPP_RECORDER_COUNTER imp_WppRecorderGetCounterHandle(void);
````

## Parameters

`WppCb`

TBD


## Return Value

ID of the counter whose current value is to be read.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wpprecorder.h |
| **Library** | NtosKrnl.exe |