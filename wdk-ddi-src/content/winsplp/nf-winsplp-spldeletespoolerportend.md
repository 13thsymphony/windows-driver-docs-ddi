---
UID: NF:winsplp.SplDeleteSpoolerPortEnd
title: SplDeleteSpoolerPortEnd function
author: windows-driver-content
description: "."
old-location: print\spldeletespoolerportend.htm
old-project: print
ms.assetid: 947391B5-5355-4ADB-B26E-A51FE0B0B85F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: SplDeleteSpoolerPortEnd, SplDeleteSpoolerPortEnd function [Print Devices], print.spldeletespoolerportend, winsplp/SplDeleteSpoolerPortEnd
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
-	Winsplp.h
api_name:
-	SplDeleteSpoolerPortEnd
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# SplDeleteSpoolerPortEnd function


## Syntax

````
BOOL WINAPI SplDeleteSpoolerPortEnd(
  _In_ PCWSTR  pName,
  _In_ BOOL    bDeletePort
);
````

## Parameters

`pName`



`bDeletePort`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |