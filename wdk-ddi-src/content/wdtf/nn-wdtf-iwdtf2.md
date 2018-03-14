---
UID: NN:wdtf.IWDTF2
title: IWDTF2
author: windows-driver-content
description: Defines properties for the WDTF collection.
old-location: dtf\iwdtf2.htm
old-project: dtf
ms.assetid: c6ac7f2b-e68e-47ed-89b7-d7704110c606
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTF2, IWDTF2 interface [Windows Device Testing Framework], IWDTF2 interface [Windows Device Testing Framework], described, Microsoft.WDTF.IWDTF2, dtf.iwdtf2, wdtf/IWDTF2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTF2
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTF2 interface

Defines properties for the WDTF collection.

## Methods

<p>The <b>IWDTF2</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IWDTF2::get_Config](nf-wdtf-iwdtf2-get_config.md) | Gets the WDTF configuration object. |
| [IWDTF2::get_DeviceDepot](nf-wdtf-iwdtf2-get_devicedepot.md) | Gets the DeviceDepot object. |
| [IWDTF2::get_Log](nf-wdtf-iwdtf2-get_log.md) | Gets the WDTF log object. |
| [IWDTF2::get_SystemDepot](nf-wdtf-iwdtf2-get_systemdepot.md) | Gets the SystemDepot object. |

## Remarks
The <b>IWDTF2</b> aggregation interface provides a single instantiation point for you to use the WDTF object. 
The user instantiates WDTF sub-objects as-needed when the corresponding properties are first accessed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows XP Professional |
| **Target Platform** | Windows |
| **Header** | wdtf.h |