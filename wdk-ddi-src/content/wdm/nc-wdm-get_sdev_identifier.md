---
UID: NC:wdm.GET_SDEV_IDENTIFIER
title: GET_SDEV_IDENTIFIER
author: windows-driver-content
description: This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release.
old-location: kernel\get_sdev_identifier.htm
old-project: kernel
ms.assetid: aaa149d8-f08d-442c-980a-9390ac8bc7f6
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: GET_SDEV_IDENTIFIER, GetSDevIdentifier, GetSDevIdentifier callback function [Kernel-Mode Driver Architecture], kernel.get_sdev_identifier, wdm/GetSDevIdentifier
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
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
-	kbSyntax
api_type:
-	<TBD>
api_location:
-
api_name:
-	GET_SDEV_IDENTIFIER callback
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# GET_SDEV_IDENTIFIER callback function
This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release.

## Syntax

```
GET_SDEV_IDENTIFIER GetSdevIdentifier;

ULONGLONG GetSdevIdentifier(
  PVOID InterfaceContext
)
{...}
```

## Parameters

`InterfaceContext`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | wdm.h (include Wdm.h) |