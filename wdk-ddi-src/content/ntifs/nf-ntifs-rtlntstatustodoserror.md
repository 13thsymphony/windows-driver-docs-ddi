---
UID: NF:ntifs.RtlNtStatusToDosError
title: RtlNtStatusToDosError function
author: windows-driver-content
description: The RtlNtStatusToDosError routine converts the specified NTSTATUS code to its equivalent system error code.
old-location: ifsk\rtlntstatustodoserror.htm
old-project: ifsk
ms.assetid: 9ba6f693-b0b7-4176-b951-7bb259bec391
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlNtStatusToDosError, ntifs/RtlNtStatusToDosError, rtlref_8afdfe24-1071-4bab-b935-b1b91eb52766.xml, RtlNtStatusToDosError routine [Installable File System Drivers], ifsk.rtlntstatustodoserror
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The RtlNtStatusToDosError routine is available on Microsoft Windows 2000 and later versions of Windows.
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlNtStatusToDosError
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlNtStatusToDosError function
The <b>RtlNtStatusToDosError</b> routine converts the specified NTSTATUS code to its equivalent system error code.

## Syntax

````
ULONG RtlNtStatusToDosError(
  _In_ NTSTATUS Status
);
````

## Parameters

`Status`

The NTSTATUS code to be converted.


## Return Value

<b>RtlNtStatusToDosError</b> returns the corresponding system error code. Error codes are defined in <i>Winerror.h</i>.

<b>RtlNtStatusToDosError</b> returns ERROR_MR_MID_NOT_FOUND when the specified NTSTATUS code does not have a corresponding system error code. For more information about system error codes, see  <a href="https://msdn.microsoft.com/4a3a8feb-a05f-4614-8f04-1f507da7e5b7">System Error Codes</a>.

## Remarks

There is no function that provides the inverse functionality of <b>RtlNtStatusToDosError</b>, converting a system error code to its corresponding NTSTATUS code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The RtlNtStatusToDosError routine is available on Microsoft Windows 2000 and later versions of Windows. The RtlNtStatusToDosError routine is available on Microsoft Windows 2000 and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |