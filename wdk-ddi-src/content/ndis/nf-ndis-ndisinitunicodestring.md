---
UID : NF:ndis.NdisInitUnicodeString
title : NdisInitUnicodeString macro
author : windows-driver-content
description : The NdisInitUnicodeString function initializes a counted Unicode string.
old-location : netvista\ndisinitunicodestring.htm
old-project : netvista
ms.assetid : 073feb91-48ae-4ad5-9061-117e6541021c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis_string_ref_a25a98b2-f88b-4a56-9bb7-77a4e6dc10a6.xml, NdisInitUnicodeString macro [Network Drivers Starting with Windows Vista], netvista.ndisinitunicodestring, NdisInitUnicodeString, ndis/NdisInitUnicodeString
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitUnicodeString (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitUnicodeString (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisInitUnicodeString function
The 
  <b>NdisInitUnicodeString</b> function initializes a counted Unicode string.

## Syntax

````
VOID NdisInitUnicodeString(
  [in, out] PNDIS_STRING DestinationString,
  [in]      PCWSTR       SourceString
);
````

## Parameters

`_us`

TBD

`s`

TBD


## Return Value

None

## Remarks

The 
    <i>DestinationString</i> is initialized to point to the 
    <i>SourceString</i> . The 
    <b>Length</b> and 
    <b>MaximumLength</b> members of NDIS_STRING for the 
    <i>DestinationString</i> are initialized to the length of the string at 
    <i>SourceString</i>. If 
    <i>SourceString</i> is <b>NULL</b>, the length is zero.

Callers of 
    <b>NdisInitUnicodeString</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the 
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

<a href="..\ndis\nf-ndis-ndisinitansistring.md">NdisInitAnsiString</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a>

<mshelp:link keywords="netvista.ndisansistringtounicodestring" tabindex="0"><b>
   NdisAnsiStringToUnicodeString</b></mshelp:link>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<mshelp:link keywords="netvista.ndisunicodestringtoansistring" tabindex="0"><b>
   NdisUnicodeStringToAnsiString</b></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>

<mshelp:link keywords="netvista.driverentry_of_ndis_protocol_drivers" tabindex="0"><b>DriverEntry of NDIS Protocol
   Drivers</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitUnicodeString macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>