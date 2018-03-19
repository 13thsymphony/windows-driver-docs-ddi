---
UID: NF:ucmtcpcidevice.UCMTCPCI_DEVICE_CONFIG_INIT
title: UCMTCPCI_DEVICE_CONFIG_INIT function
author: windows-driver-content
description: Initializes the UCMTCPCI_DEVICE_CONFIG structure.
old-location: buses\ucmtcpci_device_config_init.htm
old-project: usbref
ms.assetid: 8845f8f7-683e-487b-924b-596dbbfb98f2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCMTCPCI_DEVICE_CONFIG_INIT, UCMTCPCI_DEVICE_CONFIG_INIT method [Buses], buses.ucmtcpci_device_config_init, ucmtcpcidevice/UCMTCPCI_DEVICE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpcidevice.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpcidevice.h
api_name:
-	UCMTCPCI_DEVICE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG
req.product: Windows 10 or later.
---


# UCMTCPCI_DEVICE_CONFIG_INIT function
Initializes the <a href="..\ucmtcpcidevice\ns-ucmtcpcidevice-_ucmtcpci_device_config.md">UCMTCPCI_DEVICE_CONFIG</a> structure.

## Syntax

````
VOID UCMTCPCI_DEVICE_CONFIG_INIT(
  _Out_ PUCMTCPCI_DEVICE_CONFIG Config
);
````

## Parameters

`Config`

A pointer to the driver-allocated <a href="..\ucmtcpcidevice\ns-ucmtcpcidevice-_ucmtcpci_device_config.md">UCMTCPCI_DEVICE_CONFIG</a> structure.


## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ucmtcpcidevice.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ucmtcpcidevice\nf-ucmtcpcidevice-ucmtcpcideviceinitialize.md">UcmTcpciDeviceInitialize</a>