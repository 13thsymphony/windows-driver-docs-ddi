---
UID : NF:ntifs.CcGetFileObjectFromSectionPtrs
title : CcGetFileObjectFromSectionPtrs function
author : windows-driver-content
description : Given a pointer to the section object pointers for a cached file, the CcGetFileObjectFromSectionPtrs routine returns a pointer to the file object that the cache manager is using for the file.
old-location : ifsk\ccgetfileobjectfromsectionptrs.htm
old-project : ifsk
ms.assetid : da756f88-e2c6-4bff-8390-be48902fe130
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CcGetFileObjectFromSectionPtrs
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CcGetFileObjectFromSectionPtrs
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
req.irql : 
req.typenames : TOKEN_TYPE
---


# CcGetFileObjectFromSectionPtrs function
Given a pointer to the section object pointers for a cached file, the <b>CcGetFileObjectFromSectionPtrs</b> routine returns a pointer to the file object that the cache manager is using for the file.

## Syntax

````
PFILE_OBJECT CcGetFileObjectFromSectionPtrs(
  _In_ PSECTION_OBJECT_POINTERS SectionObjectPointer
);
````

## Parameters

`SectionObjectPointer`

Pointer to a structure containing the file object's section object pointers.


## Return Value

A pointer to the file object, or <b>NULL</b> if the file is not cached or is no longer cached.

## Remarks

The file system is responsible for ensuring that the file object remains valid while in use. It is impossible for the cache manager to guarantee this. 

By using <b>CcGetFileObjectFromSectionPtrs</b>, you lose some caching functionality. Instead, use the <a href="..\ntifs\nf-ntifs-ccgetfileobjectfromsectionptrsref.md">CcGetFileObjectFromSectionPtrsRef</a> routine, which provides the same functionality as <b>CcGetFileObjectFromSectionPtrs</b> as well as creating a reference for the object.

For more information about creating mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563682">Sections and Views</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccgetfileobjectfromsectionptrsref.md">CcGetFileObjectFromSectionPtrsRef</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetFileObjectFromSectionPtrs routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>