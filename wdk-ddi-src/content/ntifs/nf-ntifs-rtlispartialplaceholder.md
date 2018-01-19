---
UID : NF:ntifs.RtlIsPartialPlaceholder
title : RtlIsPartialPlaceholder function
author : windows-driver-content
description : The RtlIsPartialPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location : ifsk\rtlispartialplaceholder.htm
old-project : ifsk
ms.assetid : FB47F5BE-76B4-4A99-A15F-DE3E11D1DA2B
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlIsPartialPlaceholder
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 10, version 1709.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlIsPartialPlaceholder
req.alt-loc : Ntifs.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : TOKEN_TYPE
---


# RtlIsPartialPlaceholder function
The <b>RtlIsPartialPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.

## Syntax

````
BOOLEAN RtlIsPartialPlaceholder(
  _In_ ULONG FileAttributes,
  _In_ ULONG ReparseTag
);
````

## Parameters

`FileAttributes`

Specifies the file attributes of a file or directory.

`ReparseTag`

The ReparseTag or EaSize of a file or directory.


## Return Value

This function returns <b>TRUE</b> if the file or directory is a partial placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlispartialplaceholderfileinfo.md">RtlIsPartialPlaceholderFileInfo</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlispartialplaceholderfilehandle.md">RtlIsPartialPlaceholderFileHandle</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsPartialPlaceholder routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>