---
UID: NF:wpprecorder.WppRecorderLogDelete
title: WppRecorderLogDelete macro
author: windows-driver-content
description: The WppRecorderLogDelete method deletes the specified recorder log.
old-location: devtest\wpprecorderlogdelete.htm
old-project: devtest
ms.assetid: AEE10756-7301-4B55-82A5-27CA595854EA
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WppRecorderLogDelete, imp_WppRecorderLogDelete, imp_WppRecorderLogDelete function [Driver Development Tools], devtest.wpprecorderlogdelete, wpprecorder/imp_WppRecorderLogDelete
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
-	imp_WppRecorderLogDelete
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# WppRecorderLogDelete function
The <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogdelete.md">WppRecorderLogDelete</a> method deletes the specified recorder log.

## Syntax

````
NTSTATUS imp_WppRecorderLogDelete(
   NULL RecorderLog
);
````

## Parameters

`RecorderLog`

Handle to the recorder log to delete.


## Return Value

None

## Remarks

When a thread enters this function, no threads can subsequently  log to this buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wpprecorder.h |
| **Library** | wpprecorder.h |