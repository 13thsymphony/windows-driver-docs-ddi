---
UID: NF:iddcx.IDD_CX_CLIENT_CONFIG_INIT
title: IDD_CX_CLIENT_CONFIG_INIT function
author: windows-driver-content
description: Initializes the IDD_CX_CLIENT_CONFIG structure.
old-location: display\idd_cx_client_config_init.htm
old-project: display
ms.assetid: 0b2cf0d6-1d69-4917-9e97-f8f2563e6d3c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.idd_cx_client_config_init, IDD_CX_CLIENT_CONFIG_INIT, IDD_CX_CLIENT_CONFIG_INIT method [Display Devices], iddcx/IDD_CX_CLIENT_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	iddcx.h
apiname:
-	IDD_CX_CLIENT_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: 
---


# IDD_CX_CLIENT_CONFIG_INIT function
Initializes the IDD_CX_CLIENT_CONFIG structure.

## Syntax

````
VOID IDD_CX_CLIENT_CONFIG_INIT(
  _Out_ IDD_CX_CLIENT_CONFIG *Config
);
````

## Parameters

`Config`

A pointer to the driver-allocated IDD_CX_CLIENT_CONFIG structure.


## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | iddcx.h |
| **Library** | NtosKrnl.exe |