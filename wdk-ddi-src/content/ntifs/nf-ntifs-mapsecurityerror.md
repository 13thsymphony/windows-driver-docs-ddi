---
UID: NF:ntifs.MapSecurityError
title: MapSecurityError function
author: windows-driver-content
description: The MapSecurityError function maps a security interface SECURITY_STATUS status code to a corresponding NSTATUS status code.
old-location: ifsk\mapsecurityerror.htm
old-project: ifsk
ms.assetid: 899b7d6e-a17b-4030-9512-591b003ca6b2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IFSMiscRef_41a163d7-81d1-4877-b1c2-ae90b203177a.xml, MapSecurityError, MapSecurityError function [Installable File System Drivers], ifsk.mapsecurityerror, ntifs/MapSecurityError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MapSecurityError
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# MapSecurityError function
The <b>MapSecurityError</b> function maps a security interface SECURITY_STATUS status code to a corresponding NSTATUS status code.

## Syntax

````
NTSTATUS SEC_ENTRY MapSecurityError(
  _In_ SECURITY_STATUS Error
);
````

## Parameters

`SecStatus`

TBD


## Return Value

The NTSTATUS status code corresponding to the input Error status code.

## Remarks

This function maps a security interface status code of type SECURITY_STATUS to a corresponding NSTATUS status code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows 2000 and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any. |