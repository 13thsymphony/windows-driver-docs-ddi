---
UID: NS:acpiioct._ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
title: "_ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER"
author: windows-driver-content
description: This topic describes the ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure.
old-location: acpi\acpi_manipulate_global_lock_buffer.htm
old-project: acpi
ms.assetid: 841CC16D-BDFC-4A3F-9DDD-940A591EBEF2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure pointer [ACPI Devices], ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure [ACPI Devices], acpiioct/PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, acpiioct/ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, *PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, acpi.acpi_manipulate_global_lock_buffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
product: Windows
targetos: Windows
req.typenames: ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, *PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
---

# _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure
This topic describes the  <b>ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER</b> structure.

## Syntax
````
typedef struct _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER {
  ULONG Signature;
  PVOID LockObject;
} ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, *PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER;
````

## Members


`LockObject`

Defines the <b>PVOID</b> member <b>LockObject</b>.

`Signature`

Defines the <b>ULONG</b> member <b>Signature</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | acpiioct.h (include Acpiioct.h) |