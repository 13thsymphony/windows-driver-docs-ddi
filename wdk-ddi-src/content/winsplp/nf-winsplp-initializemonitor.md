---
UID: NF:winsplp.InitializeMonitor
title: InitializeMonitor function
author: windows-driver-content
description: "."
old-location: print\initializemonitor.htm
old-project: print
ms.assetid: e9d833cd-29d6-4c71-ba90-8d7dcf934420
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: winsplp/InitializeMonitor, InitializeMonitor function [Print Devices], spoolfnc_21afb8f9-70e1-478e-9ad0-cec810216b50.xml, print.initializemonitor, InitializeMonitor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
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
-	winsplp.h
apiname:
-	InitializeMonitor
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# InitializeMonitor function


## Syntax

````
BOOL WINAPI InitializeMonitor(
  _In_ LPWSTR pRegistryRoot
);
````

## Parameters

`pRegistryRoot`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |