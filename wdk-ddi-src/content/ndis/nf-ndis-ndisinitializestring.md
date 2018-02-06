---
UID: NF:ndis.NdisInitializeString
title: NdisInitializeString function
author: windows-driver-content
description: The NdisInitializeString function allocates storage for and initializes a counted string in the system-default character set.
old-location: netvista\ndisinitializestring.htm
old-project: netvista
ms.assetid: c6945d7d-5152-4968-a628-7850b8083a82
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_string_ref_886eff5e-5f5a-49f2-91d3-e87128cf0542.xml, NdisInitializeString, NdisInitializeString function [Network Drivers Starting with Windows Vista], netvista.ndisinitializestring, ndis/NdisInitializeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitUnicodeString  or RTL_CONSTANT_STRING or   DECLARE_CONST_UNICODE_STRING (see ntdef.h) instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisInitializeString
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisInitializeString function
The 
  <b>NdisInitializeString</b> function allocates storage for and initializes a counted string in the
  system-default character set.

## Syntax

````
VOID NdisInitializeString(
  _Out_ PNDIS_STRING DestinationString,
  _In_  PUCHAR       SourceString
);
````

## Parameters

`Destination`

TBD

`Source`

TBD


## Return Value

None

## Remarks

<b>NdisInitializeString</b> sets the 
    <b>Length</b> and 
    <b>MaximumLength</b> members of NDIS_STRING for the destination string and terminates the destination
    string with zero. For Windows 2000 and later drivers, 
    <b>NdisInitializeString</b> converts the supplied source string to Unicode characters.

<i>SourceString</i> must not be <b>NULL</b>.

The buffer allocated by 
    <b>NdisInitializeString</b> should be released with the 
    <a href="..\ndis\nf-ndis-ndisfreestring.md">NdisFreeString</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitUnicodeString  or RTL_CONSTANT_STRING or   DECLARE_CONST_UNICODE_STRING (see ntdef.h) instead. Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitUnicodeString  or RTL_CONSTANT_STRING or   DECLARE_CONST_UNICODE_STRING (see ntdef.h) instead. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlequalunicodestring.md">RtlEqualUnicodeString</a>

<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>

<a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>

<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlfreeansistring.md">RtlFreeAnsiString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitializeString function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>