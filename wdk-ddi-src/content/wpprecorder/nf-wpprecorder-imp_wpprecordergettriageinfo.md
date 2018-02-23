---
UID: NF:wpprecorder.imp_WppRecorderGetTriageInfo
title: imp_WppRecorderGetTriageInfo function
author: windows-driver-content
description: The WppRecorderGetTriageInfo.
old-location: devtest\wpprecordergettriageinfo.htm
old-project: devtest
ms.assetid: D2790496-1F86-4EF0-8AFE-77AC0C89EE05
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: imp_WppRecorderGetTriageInfo function [Driver Development Tools], wpprecorder/imp_WppRecorderGetTriageInfo, imp_WppRecorderGetTriageInfo, devtest.wpprecordergettriageinfo
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
-	imp_WppRecorderGetTriageInfo
product: Windows
targetos: Windows
req.typenames: "*PWNODE_HEADER, WNODE_HEADER"
req.product: Windows 10 or later.
---


# imp_WppRecorderGetTriageInfo function
The <b>WppRecorderGetTriageInfo</b> method

## Syntax

````
NTSTATUS imp_WppRecorderGetTriageInfo(
  _Out_ PWPP_TRIAGE_INFO WppTriageInfo
);
````

## Parameters

`WppCb`

TBD

`WppTriageInfo`

Pointer to a <a href="..\wpprecorder\ns-wpprecorder-_wpp_triage_info.md">WPP_TRIAGE_INFO</a> structure.


## Return Value

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> values


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wpprecorder.h |
| **Library** | NtosKrnl.exe |