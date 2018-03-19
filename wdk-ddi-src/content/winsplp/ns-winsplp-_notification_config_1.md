---
UID: NS:winsplp._NOTIFICATION_CONFIG_1
title: "_NOTIFICATION_CONFIG_1"
author: windows-driver-content
description: "."
old-location: print\notification_config_1.htm
old-project: print
ms.assetid: 4A33F3EB-9A2E-40F4-B5BC-EDEA5085301E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNOTIFICATION_CONFIG_1, NOTIFICATION_CONFIG_1, NOTIFICATION_CONFIG_1 structure [Print Devices], PNOTIFICATION_CONFIG_1, PNOTIFICATION_CONFIG_1 structure pointer [Print Devices], _NOTIFICATION_CONFIG_1, print.notification_config_1, winsplp/NOTIFICATION_CONFIG_1, winsplp/PNOTIFICATION_CONFIG_1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	NOTIFICATION_CONFIG_1
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_1, *PNOTIFICATION_CONFIG_1
req.product: Windows 10 or later.
---

# _NOTIFICATION_CONFIG_1 structure


## Syntax
````
typedef struct _NOTIFICATION_CONFIG_1 {
  UINT                   cbSize;
  DWORD                  fdwFlags;
  ROUTER_NOTIFY_CALLBACK pfnNotifyCallback;
  PVOID                  pContext;
} NOTIFICATION_CONFIG_1, *PNOTIFICATION_CONFIG_1;
````

## Members


`cbSize`



`fdwFlags`



`pfnNotifyCallback`



`pContext`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h |