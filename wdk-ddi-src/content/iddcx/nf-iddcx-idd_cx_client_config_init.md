---
UID: NF:iddcx.IDD_CX_CLIENT_CONFIG_INIT
title: IDD_CX_CLIENT_CONFIG_INIT function
author: windows-driver-content
description: Initializes the IDD_CX_CLIENT_CONFIG structure.
old-location: display\idd_cx_client_config_init.htm
old-project: display
ms.assetid: 0b2cf0d6-1d69-4917-9e97-f8f2563e6d3c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDD_CX_CLIENT_CONFIG_INIT, IDD_CX_CLIENT_CONFIG_INIT method [Display Devices], display.idd_cx_client_config_init, iddcx/IDD_CX_CLIENT_CONFIG_INIT
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
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
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | iddcx.h |