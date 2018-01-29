---
UID : NF:ntddk.IoIsFileOriginRemote
title : IoIsFileOriginRemote function
author : windows-driver-content
description : The IoIsFileOriginRemote routine determines whether a given file object is for a remote create request.
old-location : ifsk\ioisfileoriginremote.htm
old-project : ifsk
ms.assetid : 46655cbe-0483-4897-bd12-ce108af326c6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ioref_04dab537-9cd7-44be-9592-0682c0bfbd7e.xml, IoIsFileOriginRemote, IoIsFileOriginRemote routine [Installable File System Drivers], ntddk/IoIsFileOriginRemote, ifsk.ioisfileoriginremote
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : This routine is available on Microsoft Windows XP and later.
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
req.dll : NtosKrnl.exe
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# IoIsFileOriginRemote function
The <b>IoIsFileOriginRemote</b> routine determines whether a given file object is for a remote create request.

## Syntax

````
BOOLEAN IoIsFileOriginRemote(
  _In_ PFILE_OBJECT FileObject
);
````

## Parameters

`FileObject`

Pointer to a file object for the file.


## Return Value

<b>IoIsFileOriginRemote</b> returns <b>TRUE</b> if the file object was created to satisfy a remote create request, otherwise <b>FALSE</b>.

## Remarks

File system filter drivers call <b>IoIsFileOriginRemote</b> for a file object to determine whether it represents a remote create request. 

<b>IoIsFileOriginRemote</b> must be called after the create request has entirely completed. In other words, it cannot be called in the create dispatch ("pre-create") path or the create completion ("post-create") path. 

<b>IoIsFileOriginRemote</b> checks the FO_REMOTE_ORIGIN flag on the file object pointed to by <i>FileObject</i>. Network file systems set or clear this flag by calling <a href="..\ntddk\nf-ntddk-iosetfileorigin.md">IoSetFileOrigin</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h, Fltkernel.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddk\nf-ntddk-iosetfileorigin.md">IoSetFileOrigin</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoIsFileOriginRemote routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>