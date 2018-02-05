---
UID : NF:wdm.EtwProviderEnabled
title : EtwProviderEnabled function
author : windows-driver-content
description : The EtwProviderEnabled function verifies that a provider is enabled for event logging at a specified level and keyword.
old-location : devtest\etwproviderenabled.htm
old-project : devtest
ms.assetid : 28b0a40e-e8e8-4953-8a3a-f3f1b58ad80f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : EtwProviderEnabled
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : EtwProviderEnabled
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# EtwProviderEnabled function
The <b>EtwProviderEnabled</b> function verifies that a provider is enabled for event logging at a specified level and keyword.

## Syntax

````
BOOLEAN EtwProviderEnabled(
  _In_ REGHANDLE RegHandle,
  _In_ UCHAR     Level,
  _In_ ULONGLONG Keyword
);
````

## Parameters

`RegHandle`

A pointer to the event provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.

`Level`

The level at which the provider is enabled.

`Keyword`

The keyword that indicates whether the provider is enabled.


## Return Value

The function returns <b>TRUE</b> if the provider is enabled and <b>FALSE</b> if the provider is not enabled.

## Remarks

You can use the <b>EtwProviderEnabled</b> function to verify that the registered provider is enabled for any event by passing in zeros for the <i>Level</i> and <i>Keyword</i> values when you call the function. If any event is enabled, the provider is enabled. 

If an event descriptor is already available, use the <a href="..\wdm\nf-wdm-etweventenabled.md">EtwEventEnabled</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows. Available in Windows Vista and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-etweventenabled.md">EtwEventEnabled</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20EtwProviderEnabled function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>