---
UID: NF:ndis.NdisEqualString
title: NdisEqualString macro
author: windows-driver-content
description: The NdisEqualString function compares two strings, in the OS-default character set, to determine whether they are equal.
old-location: netvista\ndisequalstring.htm
old-project: netvista
ms.assetid: cc5da07d-fcd2-40f9-8ba9-d7ddf35e7b7f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisequalstring, ndis/NdisEqualString, ndis_string_ref_31191521-4693-40f9-a6e7-0c9b09bc6298.xml, NdisEqualString, NdisEqualString macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualUnicodeString instead.
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
-	NdisEqualString
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisEqualString function
The 
  <b>NdisEqualString</b> function compares two strings, in the OS-default character set, to determine whether
  they are equal.

## Syntax

````
BOOLEAN NdisEqualString(
  [in] PNDIS_STRING String1,
  [in] PNDIS_STRING String2,
  [in] BOOLEAN      CaseInsensitive
);
````

## Parameters

`_String1`

A pointer to an NDIS_STRING type that describes the first string.

`_String2`

A pointer to an NDIS_STRING type that describes the second string.

`_CaseInsensitive`

A boolean value that is <b>TRUE</b> if case should be ignored when doing the comparison. Otherwise, it is
     <b>FALSE</b>.


## Return Value

None

## Remarks

Starting with Windows 2000, a string of type NDIS_STRING is a counted, null-terminated Unicode string.
    That is, NDIS defines the NDIS_STRING type as a 
    <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualUnicodeString instead. Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualUnicodeString instead. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisEqualString macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>