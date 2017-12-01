---
UID: NS.wdm._KTMOBJECT_CURSOR
title: KTMOBJECT_CURSOR
author: windows-driver-content
description: The KTMOBJECT_CURSOR structure receives enumeration information about KTM objects when a component calls ZwEnumerateTransactionObject.
old-location: kernel\ktmobject_cursor.htm
old-project: kernel
ms.assetid: 0cfcd019-0c5b-4635-859f-741a6e4aa91d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KTMOBJECT_CURSOR, KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KTMOBJECT_CURSOR
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# KTMOBJECT_CURSOR structure



## -description
<p>The <b>KTMOBJECT_CURSOR</b> structure receives enumeration information about KTM objects when a component calls <a href="..\wdm\nf-wdm-zwenumeratetransactionobject.md">ZwEnumerateTransactionObject</a>. </p>


## -syntax

````
typedef struct _KTMOBJECT_CURSOR {
  GUID  LastQuery;
  ULONG ObjectIdCount;
  GUID  ObjectIds[1];
} KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR;
````


## -struct-fields
<dl>

### -field <b>LastQuery</b>

<dd>
<p>After <b>ZwEnumerateTransactionObject</b> returns, this member contains the GUID of the last object that <b>ZwEnumerateTransactionObject</b> enumerated. Before it calls <b>ZwEnumerateTransactionObject</b> the first time, the caller must set this value to zero.</p>
</dd>

### -field <b>ObjectIdCount</b>

<dd>
<p>After <b>ZwEnumerateTransactionObject</b> returns, this member contains the number of GUIDs that the <b>ObjectIds</b> array contains.</p>
</dd>

### -field <b>ObjectIds</b>

<dd>
<p>A caller-allocated array of GUID-typed elements. After <b>ZwEnumerateTransactionObject</b> returns, this array contains GUIDs that identify enumerated objects.</p>
</dd>
</dl>

## -remarks
<p>The <b>KTMOBJECT_CURSOR</b> structure is used at the beginning of buffers that callers pass to the <b>ZwEnumerateTransactionObject</b> routine.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later operating system versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratetransactionobject.md">ZwEnumerateTransactionObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KTMOBJECT_CURSOR structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
