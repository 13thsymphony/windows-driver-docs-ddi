---
UID: NS:ndisndk._NDIS_NDK_PROVIDER_CHARACTERISTICS
title: _NDIS_NDK_PROVIDER_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_NDK_PROVIDER_CHARACTERISTICS structure specifies NDK provider characteristics.
old-location: netvista\ndis_ndk_provider_characteristics.htm
old-project: netvista
ms.assetid: 40F07AC8-80F7-4DBC-BDC9-236530B011D4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NDIS_NDK_PROVIDER_CHARACTERISTICS, NDIS_NDK_PROVIDER_CHARACTERISTICS, *PNDIS_NDK_PROVIDER_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndisndk.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_NDK_PROVIDER_CHARACTERISTICS
req.alt-loc: ndisndk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_NDK_PROVIDER_CHARACTERISTICS, *PNDIS_NDK_PROVIDER_CHARACTERISTICS
---

# _NDIS_NDK_PROVIDER_CHARACTERISTICS structure



## -description
The <b>NDIS_NDK_PROVIDER_CHARACTERISTICS</b> structure specifies NDK provider characteristics.



## -syntax

````
typedef struct _NDIS_NDK_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER        Header;
  ULONG                     Flags;
  OPEN_NDK_ADAPTER_HANDLER  OpenNDKAdapterHandler;
  CLOSE_NDK_ADAPTER_HANDLER CloseNDKAdapterHandler;
} NDIS_NDK_PROVIDER_CHARACTERISTICS, *PNDIS_NDK_PROVIDER_CHARACTERISTICS;
````


## -struct-fields

### -field Header

An 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure that describes this
     <b>NDIS_NDK_PROVIDER_CHARACTERISTICS</b> structure. NDIS sets the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>NDIS sets the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_NDK_PROVIDER_CHARACTERISTICS</b>.</li>
<li>NDIS sets the <b>Revision</b> member to <b>NDIS_NDK_PROVIDER_CHARACTERISTICS_REVISION_1</b>.</li>
<li>NDIS sets the <b>Size</b> member to <b>NDIS_SIZEOF_NDK_PROVIDER_CHARACTERISTICS_REVISION_1</b>.</li>
</ul>

### -field Flags

Reserved, must be set to zero.


### -field OpenNDKAdapterHandler

The entry point for the <a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a> function.


### -field CloseNDKAdapterHandler

The entry point for the <a href="..\ndisndk\nc-ndisndk-close_ndk_adapter_handler.md">CLOSE_NDK_ADAPTER_HANDLER</a> function.


## -remarks
To specify entry points for NDK services and other NDK provider characteristics, NDIS miniport drivers pass a pointer to an initialized <b>NDIS_NDK_PROVIDER_CHARACTERISTICS</b> structure to the <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndisndk.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndisndk\nc-ndisndk-close_ndk_adapter_handler.md">CLOSE_NDK_ADAPTER_HANDLER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
<dt>
<a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NDK_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

