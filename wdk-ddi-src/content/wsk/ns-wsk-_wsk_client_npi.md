---
UID: NS:wsk._WSK_CLIENT_NPI
title: "_WSK_CLIENT_NPI"
author: windows-driver-content
description: The WSK_CLIENT_NPI structure identifies a Network Programming Interface (NPI) implemented by a WSK client.
old-location: netvista\wsk_client_npi.htm
old-project: netvista
ms.assetid: 2f50b228-5565-436f-8c68-8885b8916001
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWSK_CLIENT_NPI, PWSK_CLIENT_NPI, PWSK_CLIENT_NPI structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_NPI, WSK_CLIENT_NPI structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_NPI, netvista.wsk_client_npi, wsk/PWSK_CLIENT_NPI, wsk/WSK_CLIENT_NPI, wskref_e498e50c-695d-4f5c-a1db-0f87f4313d4a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_CLIENT_NPI
product:
- Windows
targetos: Windows
req.typenames: WSK_CLIENT_NPI, *PWSK_CLIENT_NPI
req.product: Windows 10 or later.
---

# _WSK_CLIENT_NPI structure
The WSK_CLIENT_NPI structure identifies a 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a> implemented by a WSK client.

## Syntax
```
typedef struct _WSK_CLIENT_NPI {
  PVOID                     ClientContext;
  CONST WSK_CLIENT_DISPATCH *Dispatch;
} *PWSK_CLIENT_NPI, WSK_CLIENT_NPI;
```

## Members


`ClientContext`

A pointer to the context for the WSK application's binding to the WSK subsystem.

`Dispatch`

A pointer to a constant 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571159">WSK_CLIENT_DISPATCH</a> structure.

## Remarks
For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wsk.h (include Wsk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571159">WSK_CLIENT_DISPATCH</a>