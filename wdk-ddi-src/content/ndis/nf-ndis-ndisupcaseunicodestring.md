---
UID: NF:ndis.NdisUpcaseUnicodeString
title: NdisUpcaseUnicodeString macro
author: windows-driver-content
description: The NdisUpcaseUnicodeString function converts a copy of a given Unicode string to upper case and returns the converted string.Note  This function is deprecated for NDIS 6.0 and later.
old-location: netvista\ndisupcaseunicodestring.htm
old-project: netvista
ms.assetid: 5f735c98-26a6-4644-9fd4-b832ac9379c2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis_string_ref_79578398-7b4c-4741-a39b-5e5e30b2f4b3.xml, NdisUpcaseUnicodeString, ndis/NdisUpcaseUnicodeString, netvista.ndisupcaseunicodestring, NdisUpcaseUnicodeString macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlUpcaseUnicodeString instead.
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
-	NdisUpcaseUnicodeString
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisUpcaseUnicodeString function
The 
  <b>NdisUpcaseUnicodeString</b> function converts a copy of a given Unicode string to upper case and returns
  the converted string.
<div class="alert"><b>Note</b>  This function is deprecated for NDIS 6.0 and later. </div><div> </div>

## Syntax

````
NTSTATUS NdisUpcaseUnicodeString(
  [out] PUNICODE_STRING DestinationString,
  [in]  PUNICODE_STRING SourceString
);
````

## Parameters

`_d`

TBD

`_s`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlUpcaseUnicodeString instead.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUpcaseUnicodeString macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>