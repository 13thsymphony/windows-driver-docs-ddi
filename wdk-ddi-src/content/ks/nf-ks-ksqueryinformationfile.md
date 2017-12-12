---
UID: NF.ks.KsQueryInformationFile
title: KsQueryInformationFile function
author: windows-driver-content
description: The KsQueryInformationFile function performs an information query against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information request against the device object.
old-location: stream\ksqueryinformationfile.htm
old-project: stream
ms.assetid: db1cce43-1eae-4af0-bb61-a5c295e3d325
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsQueryInformationFile
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
req.alt-api: KsQueryInformationFile
req.alt-loc: Ks.lib,Ks.dll
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
---

# KsQueryInformationFile function



## -description
The <b>KsQueryInformationFile</b> function performs an information query against the specified file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates an information request against the device object<i>.</i>



## -syntax

````
NTSTATUS KsQueryInformationFile(
  _In_  PFILE_OBJECT           FileObject,
  _Out_ PVOID                  FileInformation,
  _In_  ULONG                  Length,
  _In_  FILE_INFORMATION_CLASS FileInformationClass
);
````


## -parameters

### -param FileObject [in]

Specifies the file object from which to query the standard information.


### -param FileInformation [out]

Indicates the place in which to put the file information. This is assumed to be a valid or probed address.


### -param Length [in]

Specifies the correct length of the <i>FileInformation</i> buffer.


### -param FileInformationClass [in]

Specifies the class of information being requested.


## -returns
The <b>KsQueryInformationFile</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns a query error. 


## -remarks
The <b>KsQueryInformationFile</b> function should only be used in cases where the query would result in an actual request to the underlying driver. For example, <b>FilePositionInformation</b> would not generate such a request and should not be used. It assumes the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>