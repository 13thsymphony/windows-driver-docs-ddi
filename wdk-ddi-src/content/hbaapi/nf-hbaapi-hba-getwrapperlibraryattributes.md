---
UID: NF.hbaapi.HBA_GetWrapperLibraryAttributes
title: HBA_GetWrapperLibraryAttributes
author: windows-driver-content
description: The HBA_GetWrapperLibraryAttributes routine retrieves the attributes of the fibre channel HBA API library that are operating system-specific.
old-location: storage\hba_getwrapperlibraryattributes.htm
old-project: storage
ms.assetid: c40b8f20-65e9-4e43-a402-14bd30f15975
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_GetWrapperLibraryAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_GetWrapperLibraryAttributes
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
req.iface: 
---

# HBA_GetWrapperLibraryAttributes function



## -description
<p>The <b>HBA_GetWrapperLibraryAttributes</b> routine retrieves the attributes of the fibre channel HBA API library that are operating system-specific. </p>


## -syntax

````
HBA_UINT32 HBA_API HBA_GetWrapperLibraryAttributes(
  _Out_ HBA_LIBRARYATTRIBUTES *Attributes
);
````


## -parameters
<dl>

### -param <i>Attributes</i> [out]

<dd>
<p>Pointer, on return, to a structure of type <a href="..\hbaapi\ns-hbaapi-hba-libraryattributes.md">HBA_LibraryAttributes</a> that holds the attributes of the wrapper library.</p>
</dd>
</dl>

## -returns
<p>The <b>HBA_GetWrapperLibraryAttributes</b> routine returns a value that indicates the version of the specification with which the library is compliant. A value of 1 indicates version 1 of the specification. A value of 2 indicates version 2 of the specification. All other values are reserved until the future versions of the specification are published.</p>

## -remarks
<p>The <b>HBA_GetWrapperLibraryAttributes</b> routine, as defined by the T11 committee's <i>Fibre Channel HBA API</i> specification, retrieves information about a system-supplied HBA API library, and the related routine <a href="..\hbaapi\nf-hbaapi-hba-getvendorlibraryattributes.md">HBA_GetVendorLibraryAttributes</a> reports the characteristics of a system-supplied wrapper library that works with the vendor library to provide the fibre channel HBA API. </p>

<p>In particular, the <b>HBA_GetWrapperLibraryAttributes</b> routine allows the caller to determine whether a compatible library is installed. </p>

<p>Microsoft supplies both libraries, so currently they return the same information. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba-getvendorlibraryattributes.md">HBA_GetVendorLibraryAttributes</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba-libraryattributes.md">HBA_LibraryAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetWrapperLibraryAttributes routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
