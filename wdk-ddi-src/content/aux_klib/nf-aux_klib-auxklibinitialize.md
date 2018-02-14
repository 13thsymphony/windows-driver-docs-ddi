---
UID: NF:aux_klib.AuxKlibInitialize
title: AuxKlibInitialize function
author: windows-driver-content
description: The AuxKlibInitialize routine initializes the Auxiliary Kernel-Mode Library.
old-location: kernel\auxklibinitialize.htm
old-project: kernel
ms.assetid: 7e15cbe1-17f7-4df7-9273-9a365d309d03
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: aux_klib_d83fd3ae-3a26-4798-9ef8-1530adb78543.xml, kernel.auxklibinitialize, aux_klib/AuxKlibInitialize, AuxKlibInitialize, AuxKlibInitialize routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Aux_Klib.lib
-	Aux_Klib.dll
apiname:
-	AuxKlibInitialize
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---


# AuxKlibInitialize function
The <b>AuxKlibInitialize</b> routine initializes the <a href="https://msdn.microsoft.com/34ed3c98-6b27-47d1-bd8d-38e280abfe64">Auxiliary Kernel-Mode Library</a>.

## Syntax

````
NTSTATUS AuxKlibInitialize(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>AuxKlibInitialize</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the routine returns an appropriate NTSTATUS value.

## Remarks

Drivers that use the Auxiliary Kernel-Mode Library must call <b>AuxKlibInitialize</b> before calling any of the library's other routines.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 2000. Supported starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | aux_klib.h (include Aux_klib.h) |
| **Library** | Aux_Klib.lib |