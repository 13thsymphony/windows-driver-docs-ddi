---
UID: NF:wdm.EtwWriteString
title: EtwWriteString function
author: windows-driver-content
description: The EventWriteString function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement.
old-location: devtest\etwwritestring.htm
old-project: devtest
ms.assetid: 25de7729-f43f-4d16-a379-e1cb1ab8616c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EtwWriteString, EtwWriteString function [Driver Development Tools], devtest.etwwritestring, etw_km_b4cb697f-3523-4730-8df5-1faf201af7f8.xml, wdm/EtwWriteString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: Any level (See Comments section.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	EtwWriteString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# EtwWriteString function
The <b>EventWriteString</b> function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement.

## Syntax

````
NTSTATUS EtwWriteString(
  _In_     REGHANDLE RegHandle,
  _In_     UCHAR     Level,
  _In_     ULONGLONG Keyword,
  _In_opt_ LPCGUID   ActivityId,
  _In_     PCWSTR    String
);
````

## Parameters

`RegHandle`

A Pointer to the event provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.

`Level`

The level at which the event is active.

`Keyword`

The keyword for the event. A keyword is a bitmask that makes general statements about the category of the event or error. Because the keyword is a bitmask, you can apply more than one keyword to a single event. You can define the keywords and bit positions, or you can use Windows-standard keywords, or you can use combination of your own keywords and the Windows keywords.

`ActivityId`

The identifier that indicates the activity associated with the event. The <i>ActivityId</i> provides a way to group related events and is used in end-to-end tracing. This identifier is optional and can be <b>NULL</b>.

`String`

A null-terminated string (WCHAR).


## Return Value

The function returns STATUS_SUCCESS if the event is published successfully.

## Remarks

Because the string produced by <b>EventWriteString</b> function is not localizable, this function is not recommended for use in production code. This function should not be used to log highly visible events.

You can call <b>EtwWriteString</b> at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the <b>EtwWrite</b>, <a href="..\wdm\nf-wdm-etwwriteex.md">EtwWriteEx</a>, <b>EtwWriteString</b>,  and <b>EtwWriteTransfer</b> functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory. Data passed to the <b>EtwWrite</b>, <b>EtwWriteEx</b>, <b>EtwWriteString</b>, and <b>EtwWriteTransfer</b> functions must reside in system-space memory, regardless of what the IRQL is.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (See Comments section.) |

## See Also

<a href="..\wdm\nf-wdm-etwwrite.md">EtwWrite</a>



<a href="..\wdm\nf-wdm-etwwritetransfer.md">EtwWriteTransfer</a>



<a href="..\wdm\nf-wdm-etwwriteex.md">EtwWriteEx</a>