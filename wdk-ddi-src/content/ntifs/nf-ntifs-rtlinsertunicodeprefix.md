---
UID : NF:ntifs.RtlInsertUnicodePrefix
title : RtlInsertUnicodePrefix function
author : windows-driver-content
description : The RtlInsertUnicodePrefix routine inserts a new element into a Unicode prefix table.
old-location : ifsk\rtlinsertunicodeprefix.htm
old-project : ifsk
ms.assetid : d8a2fa19-8f44-4088-b515-69c9f2119714
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlInsertUnicodePrefix
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Windows XP
req.target-min-winversvr : Windows Server 2003
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlInsertUnicodePrefix
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
req.irql : < DISPATCH_LEVEL
req.typenames : TOKEN_TYPE
---


# RtlInsertUnicodePrefix function
The <b>RtlInsertUnicodePrefix</b> routine inserts a new element into a Unicode prefix table.

## Syntax

````
BOOLEAN RtlInsertUnicodePrefix(
  _In_  PUNICODE_PREFIX_TABLE       PrefixTable,
  _In_  PUNICODE_STRING             Prefix,
  _Out_ PUNICODE_PREFIX_TABLE_ENTRY PrefixTableEntry
);
````

## Parameters

`PrefixTable`

Pointer to the prefix table. The table must have been initialized by calling <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>.

`Prefix`

Pointer to the name string to be inserted with the element at <i>PrefixTableEntry</i>.

`PrefixTableEntry`

Pointer to caller-allocated storage, which must be at least <b>sizeof</b>(UNICODE_PREFIX_TABLE_ENTRY), for the element to be inserted for the new prefix. <b>RtlInsertUnicodePrefix</b> initializes this element, which should be considered opaque by the caller.


## Return Value

<b>RtlInsertUnicodePrefix</b> returns <b>TRUE</b> if the new element was inserted in the prefix table, or it returns <b>FALSE</b> if a duplicate element already exists in the prefix table.

## Remarks

Each prefix entry in the table is a pathname relative to the root directory of a file system volume. To be well-formed, the prefix must begin with a single backslash (\). 

After inserting the new element, <b>RtlInsertUnicodePrefix</b> rebalances the prefix table's splay tree.

File systems must call <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | < DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlfindunicodeprefix.md">RtlFindUnicodePrefix</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlnextunicodeprefix.md">RtlNextUnicodePrefix</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlremoveunicodeprefix.md">RtlRemoveUnicodePrefix</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInsertUnicodePrefix routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>