---
UID: NF:wpprecorder.imp_WppRecorderLinkCounters
title: imp_WppRecorderLinkCounters function
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
-	imp_WppRecorderLinkCounters
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# imp_WppRecorderLinkCounters function
The <b>WppRecorderLinkCounters</b> method  uses a sequence number to merge logs captured in different buffers by a driver.

## Syntax

````
NTSTATUS imp_WppRecorderLinkCounters(
  _In_ WPP_RECORDER_COUNTER CounterOwner
);
````

## Parameters

`WppCb`

TBD

`CounterOwner`

ID of the counter whose current value is to be read.


## Return Value

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> values


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wpprecorder.h |
| **Library** | NtosKrnl.exe |