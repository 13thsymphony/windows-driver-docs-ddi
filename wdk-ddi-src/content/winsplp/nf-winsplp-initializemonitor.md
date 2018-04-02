---
UID: NF:winsplp.InitializeMonitor
title: InitializeMonitor function
author: windows-driver-content
description: "."
old-location: print\initializemonitor.htm
old-project: print
ms.assetid: e9d833cd-29d6-4c71-ba90-8d7dcf934420
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: InitializeMonitor, InitializeMonitor function [Print Devices], print.initializemonitor, spoolfnc_21afb8f9-70e1-478e-9ad0-cec810216b50.xml, winsplp/InitializeMonitor
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	InitializeMonitor
product:
- Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# InitializeMonitor function


## Syntax

```
BOOL InitializeMonitor(
  LPWSTR pRegistryRoot
);
```

## Parameters

`pRegistryRoot`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |