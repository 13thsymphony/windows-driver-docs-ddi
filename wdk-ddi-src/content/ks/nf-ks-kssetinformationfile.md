---
UID: NF:ks.KsSetInformationFile
title: KsSetInformationFile function
author: windows-driver-content
description: The KsSetInformationFile function performs an information set against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information set against the device object.
old-location: stream\kssetinformationfile.htm
old-project: stream
ms.assetid: 878c6565-99f9-4f45-abba-ba4ece5b5743
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsSetInformationFile
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
req.alt-api: KsSetInformationFile
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
req.typenames: 
---

# KsSetInformationFile function



## -description
The <b>KsSetInformationFile</b> function performs an information set against the specified file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates an information set against the device object.



## -syntax

````
NTSTATUS KsSetInformationFile(
  _In_ PFILE_OBJECT           FileObject,
  _In_ PVOID                  FileInformation,
  _In_ ULONG                  Length,
  _In_ FILE_INFORMATION_CLASS FileInformationClass
);
````


## -parameters

### -param FileObject [in]

Specifies the file object to set the standard information on.


### -param FileInformation [in]

Indicates the place in which to put the file information. The file information is assumed to be a valid or probed address.


### -param Length [in]

Specifies the correct length of the <i>FileInformation</i> buffer.


### -param FileInformationClass [in]

Specifies the class of information being set.


## -returns
The <b>KsSetInformationFile</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns a set error.


## -remarks
The <b>KsSetInformationFile</b> function should be used only when the set would result in an actual request to the underlying driver, not including complex operations that require additional parameters to be sent to the driver such as rename, deletion, and completion. For example, <b>FilePositionInformation</b> would not generate such a request and should not be used. It assumes the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object.


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