---
UID : NF:ntifs.FsRtlSupportsPerFileContexts
title : FsRtlSupportsPerFileContexts macro
author : windows-driver-content
description : The FsRtlSupportsPerFileContexts macro checks if per file context information is supported by the file system that is associated with a specified FILE_OBJECT.
old-location : ifsk\fsrtlsupportsperfilecontexts.htm
old-project : ifsk
ms.assetid : 28f0e98f-1f7b-4dcf-8151-e13981634617
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : fsrtlref_98e99a7a-c80d-43d5-a0f6-3eea35a8d20a.xml, FsRtlSupportsPerFileContexts, ntifs/FsRtlSupportsPerFileContexts, FsRtlSupportsPerFileContexts function [Installable File System Drivers], ifsk.fsrtlsupportsperfilecontexts
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ntifs.h
req.include-header : FltKernel.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating system.
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
req.lib : ntifs.h
req.dll : 
req.irql : Any
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# FsRtlSupportsPerFileContexts function
The <b>FsRtlSupportsPerFileContexts</b> macro checks if per file context information is supported by the file system that is associated with a specified <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>.

## Syntax

````
BOOLEAN FsRtlSupportsPerFileContexts(
   FILE_OBJECT FileObject
);
````

## Parameters

`_fo`

TBD


## Return Value

None

## Remarks

None

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>

<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlSupportsPerFileContexts  function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>