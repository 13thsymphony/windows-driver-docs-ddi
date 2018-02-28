---
UID: NS:wsk._WSK_REGISTRATION
title: "_WSK_REGISTRATION"
author: windows-driver-content
description: The WSK_REGISTRATION structure is used by the WSK subsystem to register or unregister a WSK application as a WSK client.
old-location: netvista\wsk_registration.htm
old-project: netvista
ms.assetid: 770c53bb-5e11-4bd4-a175-6ea6ae0bb782
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWSK_REGISTRATION, PWSK_REGISTRATION, PWSK_REGISTRATION structure pointer [Network Drivers Starting with Windows Vista], WSK_REGISTRATION, WSK_REGISTRATION structure [Network Drivers Starting with Windows Vista], _WSK_REGISTRATION, netvista.wsk_registration, wsk/PWSK_REGISTRATION, wsk/WSK_REGISTRATION, wskref_1ad5b68d-5a86-476c-aa04-0f11db552a01.xml"
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
-	WSK_REGISTRATION
product: Windows
targetos: Windows
req.typenames: WSK_REGISTRATION, *PWSK_REGISTRATION
req.product: Windows 10 or later.
---

# _WSK_REGISTRATION structure
The WSK_REGISTRATION structure is used by the WSK subsystem to register or unregister a WSK
  application as a WSK client.

## Syntax
````
typedef struct _WSK_REGISTRATION {
  ULONGLONG  ReservedRegistrationState;
  PVOID      ReservedRegistrationContext;
  KSPIN_LOCK ReservedRegistrationLock;
} WSK_REGISTRATION, *PWSK_REGISTRATION;
````

## Members


`ReservedRegistrationContext`

Reserved for system use. Do not use.

`ReservedRegistrationLock`

Reserved for system use. Do not use.

`ReservedRegistrationState`

Reserved for system use. Do not use.

## Remarks
This structure is provided by a client application to register or unregister a WSK client instance. Do
    not update any of the members of this structure.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wsk.h (include Wsk.h) |