---
UID : NF:ndis.NdisInitAnsiString
title : NdisInitAnsiString macro
author : windows-driver-content
description : The NdisInitAnsiString function initializes a counted ANSI string.
old-location : netvista\ndisinitansistring.htm
old-project : netvista
ms.assetid : e8209781-36b1-4008-94bb-82bdb16f20bf
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisInitAnsiString
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlInitString instead.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisInitAnsiString
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : See Remarks section
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisInitAnsiString function
The 
  <b>NdisInitAnsiString</b> function initializes a counted ANSI string.

## Syntax

````
VOID NdisInitAnsiString(
  [in, out] PANSI_STRING DestinationString,
  [in]      PCSTR        SourceString
);
````

## Parameters

`_as`



`s`




## Return Value

None

## Remarks

The 
    <i>DestinationString</i> is initialized to point to the 
    <i>SourceString</i>. The length and maximum length for the 
    <i>DestinationString</i> are initialized to the length of the string at 
    <i>SourceString</i>. If 
    <i>SourceString</i> is <b>NULL</b>, the length is zero.

Callers of 
    <b>NdisInitAnsiString</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the 
    <i>DestinationString</i> buffer is allocated from nonpaged memory. Usually, callers are running at IRQL =
    PASSIVE_LEVEL during driver initialization.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | See Remarks section |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitAnsiString macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>