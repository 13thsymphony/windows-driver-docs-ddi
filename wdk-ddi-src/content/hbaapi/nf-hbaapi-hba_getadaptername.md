---
UID: NF.hbaapi.HBA_GetAdapterName
title: HBA_GetAdapterName function
author: windows-driver-content
description: The HBA_GetAdapterName routine retrieves the text string that identifies the HBA name that corresponds to the indicated adapter index.
old-location: storage\hba_getadaptername.htm
old-project: storage
ms.assetid: ec17efca-2cb9-4ab4-b98f-7319f6145e4e
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_GetAdapterName
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
req.alt-api: HBA_GetAdapterName
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
---

# HBA_GetAdapterName function



## -description
The <b>HBA_GetAdapterName</b> routine retrieves the text string that identifies the HBA name that corresponds to the indicated adapter index.


## -syntax

````
HBA_STATUS HBA_API HBA_GetAdapterName(
  _In_    HBA_UINT32 AdapterIndex,
  _Inout_ PCHAR      AdapterName
);
````


## -parameters

### -param AdapterIndex [in]

Indicates the index of the HBA for which the name will be returned.

### -param AdapterName [in, out]

Pointer to memory area in which the HBA name will be returned. The HBA name will be a string of the form
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>mfgdomain-model-adapterindex</pre>
</td>
</tr>
</table></span></div>
where <b>mfgdomain</b> is derived from the domain name owned by the manufacturer of the HBA, <b>model</b> is a vendor-specific identifier of the HBA product model, and <b>adapterindex</b> is a decimal representation of the HBA index in <i>AdapterIndex. </i>For example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>com.HotBiscuitsAdapters-HBA1040A-1</pre>
</td>
</tr>
</table></span></div>
For a description of the formatting of the adapter name, see the <i>Fibre Channel HBA API</i> specification published by the T11 committee.

## -returns
The <b>HBA_GetAdapterName</b> routine returns a value of type <a href="storage.hba_status">HBA_STATUS</a> that indicates the status of the HBA.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
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
<a href="..\hbaapi\ns-hbaapi-hba_adapterattributes.md">HBA_AdapterAttributes</a>
</dt>
<dt>
<a href="storage.hba_openadapter">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetAdapterName routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
