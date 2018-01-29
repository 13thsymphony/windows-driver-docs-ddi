---
UID : NF:wdm.RtlUpcaseUnicodeChar
title : RtlUpcaseUnicodeChar function
author : windows-driver-content
description : The RtlUpcaseUnicodeChar routine converts the specified Unicode character to uppercase.
old-location : kernel\rtlupcaseunicodechar.htm
old-project : kernel
ms.assetid : e8584c60-57ba-4b9c-949f-041bb37dfb13
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlUpcaseUnicodeChar, RtlUpcaseUnicodeChar routine [Kernel-Mode Driver Architecture], wdm/RtlUpcaseUnicodeChar, kernel.rtlupcaseunicodechar, k109_81806669-d742-4cb9-b4dd-d7e40fef171a.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
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
req.dll : NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlUpcaseUnicodeChar function
The <b>RtlUpcaseUnicodeChar</b> routine converts the specified Unicode character to uppercase.

## Syntax

````
WCHAR RtlUpcaseUnicodeChar(
  _In_ WCHAR SourceCharacter
);
````

## Parameters

`SourceCharacter`

Specifies the character to convert.


## Return Value

<b>RtlUpcaseUnicodeChar</b> returns the uppercase version of the specified Unicode character.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddk\nf-ntddk-rtlupcaseunicodestring.md">RtlUpcaseUnicodeString</a>

<a href="..\ntddk\nf-ntddk-rtlupperchar.md">RtlUpperChar</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUpcaseUnicodeChar routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>