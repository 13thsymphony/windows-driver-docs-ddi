---
UID : NF:winsplp.RouterAllocBidiMem
title : RouterAllocBidiMem function
author : windows-driver-content
description : RouterAllocBidiMem allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects.
old-location : print\routerallocbidimem.htm
old-project : print
ms.assetid : 39042c66-3db1-41bd-b06d-12aefcb007d3
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : winsplp/RouterAllocBidiMem, print.routerallocbidimem, RouterAllocBidiMem function [Print Devices], RouterAllocBidiMem, spoolfnc_ed433d21-ccfa-4061-9fbd-3bf333e12b31.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winsplp.h
req.include-header : Winsplp.h
req.target-type : Desktop
req.target-min-winverclnt : This function is available in Windows XP and later operating systems.
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
req.lib : Spoolss.lib
req.dll : Spoolss.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NOTIFICATION_CONFIG_FLAGS
req.product : Windows 10 or later.
---


# RouterAllocBidiMem function
<code>RouterAllocBidiMem</code> allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects.

## Syntax

````
PVOID RouterAllocBidiMem(
  _In_ size_t NumBytes
);
````

## Parameters

`NumBytes`

Specifies the size, in bytes, of the block of memory to be allocated.


## Return Value

<code>RouterAllocBidiMem</code> returns a pointer to the block of memory if successful. If the function fails, the caller can obtain the error code by calling <b>GetLastError</b> (described in the Microsoft Windows SDK documentation).

## Remarks

When the memory allocated by this function is no longer needed, it can be returned by a call to <a href="..\winsplp\nf-winsplp-routerfreebidimem.md">RouterFreeBidiMem</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This function is available in Windows XP and later operating systems. This function is available in Windows XP and later operating systems. |
| **Target Platform** | Desktop |
| **Header** | winsplp.h (include Winsplp.h) |
| **Library** | Spoolss.lib |
| **DLL** | Spoolss.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562071">SendRecvBidiDataFromPort</a>

<a href="..\winsplp\nf-winsplp-routerfreebidimem.md">RouterFreeBidiMem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RouterAllocBidiMem function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>