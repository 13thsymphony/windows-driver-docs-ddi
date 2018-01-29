---
UID : NF:ntifs.RtlNtStatusToDosErrorNoTeb
title : RtlNtStatusToDosErrorNoTeb function
author : windows-driver-content
description : Reserved for system use.
old-location : ifsk\rtlntstatustodoserrornoteb.htm
old-project : ifsk
ms.assetid : be22fb7f-408a-44ee-ae83-0f1dadcec87f
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlNtStatusToDosError routine [Installable File System Drivers], RtlNtStatusToDosError, rtlref_161ea08b-d596-4a3c-ab9b-b66f757e4415.xml, ntifs/RtlNtStatusToDosError, RtlNtStatusToDosErrorNoTeb, ifsk.rtlntstatustodoserrornoteb
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : The RtlNtStatusToDosErrorNoTeb routine is available on Microsoft Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "< DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# RtlNtStatusToDosErrorNoTeb function
The <b>RtlNtStatusToDosErrorNoTeb</b>  routine converts the specified NTSTATUS code to its equivalent system error code. Reserved for system use.

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

<b>RtlNtStatusToDosErrorNoTeb</b> returns the corresponding system error code. Error codes are defined in <i>Winerror.h</i>.

## Remarks

There is no function that provides the inverse functionality of <b>RtlNtStatusToDosErrorNoTeb</b>, converting a system error code to its corresponding NTSTATUS code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | < DISPATCH_LEVEL |
| **DDI compliance rules** |  |