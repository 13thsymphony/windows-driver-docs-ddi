---
UID: NF.ksproxy.IKsPropertySet.QuerySupported
title: IKsPropertySet::QuerySupported
author: windows-driver-content
description: The QuerySupported method determines whether a KS object supports a property set and the type of that support.
old-location: stream\ikspropertyset_querysupported.htm
old-project: stream
ms.assetid: 8b59da4f-0beb-46e8-913d-b992fa9f694d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IKsPropertySet, QuerySupported, IKsPropertySet::QuerySupported
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h, Ksproxy.h, Dsound.h, Ksproxy.h, Ksproxy.h, Dsound.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsPropertySet.QuerySupported
req.alt-loc: ksproxy.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: IKsPropertySet
---

# IKsPropertySet::QuerySupported method



## -description
<p>The <b>QuerySupported</b> method determines whether a KS object supports a property set and the type of that support.</p>


## -syntax

````
HRESULT QuerySupported(
  [in]  REFGUID PropSet,
  [in]  ULONG   Id,
  [out] ULONG   *TypeSupport
);
````


## -parameters
<dl>

### -param PropSet [in]

<dd>
<p>GUID that identifies the property set.</p>
</dd>

### -param Id [in]

<dd>
<p>Identifier of the property within the property set. </p>
</dd>

### -param TypeSupport [out]

<dd>
<p>Pointer to a variable that receives a bitmask enumerating the flags that indicate the support that the underlying driver provides. A driver can support a bitwise OR combination of the following flags: </p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>KSPROPERTY_SUPPORT_GET</p>
</td>
<td>
<p>Supports retrieving a property. Use the <a href="stream.ikspropertyset_get">IKsPropertySet::Get</a> method to retrieve the property.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_SUPPORT_SET</p>
</td>
<td>
<p>Supports setting a property. Use the <a href="stream.ikspropertyset_set">IKsPropertySet::Set</a> method to set the property.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful; otherwise, returns one of the following error codes:</p><dl>
<dt><b>E_NOTIMPL</b></dt>
</dl><p>Property set is not supported. </p><dl>
<dt><b>E_PROP_ID_UNSUPPORTED</b></dt>
</dl><p>Property identifier (<i>Id</i>) is not supported for the specified property set.</p><dl>
<dt><b>E_PROP_SET_UNSUPPORTED</b></dt>
</dl><p>Property set is not supported.</p>

<p> </p>

## -remarks
<p>KS objects include, for example, KS filters, KS pins, and KS clocks. </p><p class="note">Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.</p><p class="note">

If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.

</p>

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
<dt>Ksproxy.h (include Ksproxy.h, Ksproxy.h, Dsound.h, Ksproxy.h, Ksproxy.h, or Dsound.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ikspropertyset_get">IKsPropertySet::Get</a>
</dt>
<dt>
<a href="stream.ikspropertyset_set">IKsPropertySet::Set</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPropertySet::QuerySupported method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
