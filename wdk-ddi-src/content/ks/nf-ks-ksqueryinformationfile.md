---
UID: NF:ks.KsQueryInformationFile
title: KsQueryInformationFile function
author: windows-driver-content
description: The KsQueryInformationFile function performs an information query against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information request against the device object.
old-location: stream\ksqueryinformationfile.htm
old-project: stream
ms.assetid: db1cce43-1eae-4af0-bb61-a5c295e3d325
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsQueryInformationFile, KsQueryInformationFile function [Streaming Media Devices], ks/KsQueryInformationFile, ksfunc_3d343664-3fda-4612-96d4-3fe36532c99e.xml, stream.ksqueryinformationfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsQueryInformationFile
product: Windows
targetos: Windows
req.typenames: 
---


# KsQueryInformationFile function
The <b>KsQueryInformationFile</b> function performs an information query against the specified file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates an information request against the device object<i>.</i>

## Syntax

````
NTSTATUS KsQueryInformationFile(
  _In_  PFILE_OBJECT           FileObject,
  _Out_ PVOID                  FileInformation,
  _In_  ULONG                  Length,
  _In_  FILE_INFORMATION_CLASS FileInformationClass
);
````

## Parameters

`FileObject`

Specifies the file object from which to query the standard information.

`FileInformation`

Indicates the place in which to put the file information. This is assumed to be a valid or probed address.

`Length`

Specifies the correct length of the <i>FileInformation</i> buffer.

`FileInformationClass`

Specifies the class of information being requested.


## Return Value

The <b>KsQueryInformationFile</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns a query error.

## Remarks

The <b>KsQueryInformationFile</b> function should only be used in cases where the query would result in an actual request to the underlying driver. For example, <b>FilePositionInformation</b> would not generate such a request and should not be used. It assumes the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |