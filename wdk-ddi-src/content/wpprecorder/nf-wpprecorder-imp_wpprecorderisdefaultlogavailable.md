---
UID: NF:wpprecorder.imp_WppRecorderIsDefaultLogAvailable
title: imp_WppRecorderIsDefaultLogAvailable function
author: windows-driver-content
description: The WppRecorderIsDefaultLogAvailable method determines whether the default log is available.
old-location: devtest\wpprecorderisdefaultlogavailable.htm
old-project: devtest
ms.assetid: 5685540F-B4C4-4ED9-B783-85A898EC5A62
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: imp_WppRecorderIsDefaultLogAvailable, devtest.wpprecorderisdefaultlogavailable, wpprecorder/imp_WppRecorderIsDefaultLogAvailable, imp_WppRecorderIsDefaultLogAvailable function [Driver Development Tools], WppRecorderIsDefaultLogAvailable
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
-	imp_WppRecorderIsDefaultLogAvailable
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# imp_WppRecorderIsDefaultLogAvailable function
The <b>WppRecorderIsDefaultLogAvailable</b> method determines whether the default log is available.

## Syntax

````
BOOLEAN imp_WppRecorderIsDefaultLogAvailable(void);
````

## Parameters

`WppCb`

TBD


## Return Value

TRUE if the default log is available; otherwise, FALSE.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wpprecorder.h |
| **Library** | NtosKrnl.exe |