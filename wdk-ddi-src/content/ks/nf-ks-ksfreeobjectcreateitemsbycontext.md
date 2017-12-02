---
UID: NF.ks.KsFreeObjectCreateItemsByContext
title: KsFreeObjectCreateItemsByContext
author: windows-driver-content
description: Frees all create items with a specific context.
old-location: stream\ksfreeobjectcreateitemsbycontext.htm
old-project: stream
ms.assetid: 70c2942d-1225-4a50-b734-27995b4481d1
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsFreeObjectCreateItemsByContext
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
req.alt-api: KsFreeObjectCreateItemsByContext
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
req.iface: 
---

# KsFreeObjectCreateItemsByContext function



## -description
<p>Frees all create items with a specific context.</p>


## -syntax

````
NTSTATUS KsFreeObjectCreateItemsByContext(
  _In_ KSDEVICE_HEADER Header,
  _In_ PVOID           Context
);
````


## -parameters
<dl>

### -param Header [in]

<dd>
<p>Points to the device header on which the create items are attached.</p>
</dd>

### -param Context [in]

<dd>
<p>Contains the context of the create items to free. All create items with this context value will be freed.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if the item was freed, else STATUS_OBJECT_NAME_NOT_FOUND.</p>

## -remarks
<p>Instead of freeing create items by name as <b>KsFreeObjectCreateItems</b> does, this function will free all create items with a specific context.  For example, all create items associated with a filter factory will have the factory as context and can be freed simultaneously with this call instead of one at a time. Note that this function does not assume that the caller is serializing multiple changes to the create entry list.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksfreeobjectcreateitem.md">KsFreeObjectCreateItem</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFreeObjectCreateItemsByContext function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
