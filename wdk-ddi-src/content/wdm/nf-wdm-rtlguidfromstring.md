---
UID : NF:wdm.RtlGUIDFromString
title : RtlGUIDFromString function
author : windows-driver-content
description : The RtlGUIDFromString routine converts the given Unicode string to a GUID in binary format.
old-location : kernel\rtlguidfromstring.htm
old-project : kernel
ms.assetid : 7bdfc781-93d6-4f49-95f1-46f102908ec5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlGUIDFromString
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlGUIDFromString
req.alt-loc : NtosKrnl.exe,Ntdll.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql : PASSIVE_LEVEL
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlGUIDFromString function
The <b>RtlGUIDFromString</b> routine converts the given Unicode string to a GUID in binary format.

## Syntax

````
NTSTATUS RtlGUIDFromString(
  _In_  PCUNICODE_STRING GuidString,
  _Out_ GUID             *Guid
);
````

## Parameters

`GuidString`

Pointer to the buffered Unicode string to be converted to a GUID.

`Guid`

Pointer to a caller-supplied variable in which the GUID is returned.


## Return Value

If the conversion succeeds, <b>RtlGUIDFromString</b> returns STATUS_SUCCESS. Otherwise, no conversion was done.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlstringfromguid.md">RtlStringFromGUID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlGUIDFromString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>