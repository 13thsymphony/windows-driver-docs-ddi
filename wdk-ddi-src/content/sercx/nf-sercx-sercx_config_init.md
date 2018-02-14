---
UID: NF:sercx.SERCX_CONFIG_INIT
title: SERCX_CONFIG_INIT function
author: windows-driver-content
description: The SERCX_CONFIG_INIT function initializes a SERCX_CONFIG structure.
old-location: serports\sercx_config_init.htm
old-project: serports
ms.assetid: C7442A59-6D7C-4551-B0E4-F1E8A5BEB4B7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SERCX_CONFIG_INIT, SERCX_CONFIG_INIT function [Serial Ports], 1/SERCX_CONFIG_INIT, serports.sercx_config_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1.0\Sercx.h
apiname:
-	SERCX_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SERCX_CONFIG_INIT function
The <b>SERCX_CONFIG_INIT</b> function initializes a <a href="..\sercx\ns-sercx-_sercx_config.md">SERCX_CONFIG</a> structure.

## Syntax

````
VOID SERCX_CONFIG_INIT(
  _Out_ SERCX_CONFIG *Config
);
````

## Parameters

`Config`

A pointer to the <b>SERCX_CONFIG</b> structure that is to be initialized.


## Return Value

None.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any IRQL |

## See Also

<a href="..\sercx\ns-sercx-_sercx_config.md">SERCX_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX_CONFIG_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>