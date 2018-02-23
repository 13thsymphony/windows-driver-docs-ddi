---
UID: NF:wpprecorder.WppRecorderLinkCounters
title: WppRecorderLinkCounters macro
author: windows-driver-content
description: The WppRecorderLinkCounters.
old-location: devtest\wpprecorderlinkcounters.htm
old-project: devtest
ms.assetid: D8FF1E87-EB3E-491E-9649-076376C272B3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: devtest.wpprecorderlinkcounters, imp_WppRecorderLinkCounters, WppRecorderLinkCounters, imp_WppRecorderLinkCounters function [Driver Development Tools], wpprecorder/imp_WppRecorderLinkCounters
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
-	wpprecorder.h
apiname:
-	imp_WppRecorderLinkCounters
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# WppRecorderLinkCounters function
The <b>WppRecorderLinkCounters</b> method  uses a sequence number to merge logs captured in different buffers by a driver.

## Syntax

````
NTSTATUS imp_WppRecorderLinkCounters(
  _In_ WPP_RECORDER_COUNTER CounterOwner
);
````

## Parameters

`CounterOwner`

ID of the counter whose current value is to be read.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wpprecorder.h |
| **Library** | wpprecorder.h |