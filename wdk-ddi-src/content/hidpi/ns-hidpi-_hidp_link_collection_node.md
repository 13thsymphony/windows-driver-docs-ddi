---
UID: NS.HIDPI._HIDP_LINK_COLLECTION_NODE
title: _HIDP_LINK_COLLECTION_NODE
author: windows-driver-content
description: The HIDP_LINK_COLLECTION_NODE structure contains information about a link collection in a top-level collection's link collection array.
old-location: hid\hidp_link_collection_node.htm
old-project: hid
ms.assetid: 66ffd219-4a62-404d-ba51-4a91eccfcf96
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HIDP_LINK_COLLECTION_NODE, HIDP_LINK_COLLECTION_NODE, *PHIDP_LINK_COLLECTION_NODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HIDP_LINK_COLLECTION_NODE
req.alt-loc: hidpi.h
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
---

# _HIDP_LINK_COLLECTION_NODE structure



## -description
The HIDP_LINK_COLLECTION_NODE structure contains information about a <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="hid.link_collections#ddk_link_collection_array_kg#ddk_link_collection_array_kg">link collection array</a>.



## -syntax

````
typedef struct _HIDP_LINK_COLLECTION_NODE {
  USAGE  LinkUsage;
  USAGE  LinkUsagePage;
  USHORT Parent;
  USHORT NumberOfChildren;
  USHORT NextSibling;
  USHORT FirstChild;
  ULONG  CollectionType  :8;
  ULONG  IsAlias  :1;
  ULONG  Reserved  :23;
  PVOID  UserContext;
} HIDP_LINK_COLLECTION_NODE, *PHIDP_LINK_COLLECTION_NODE;
````


## -struct-fields

### -field LinkUsage

Specifies the <a href="hid.hid_usages#usage_id#usage_id">usage ID</a> of a top-level collection.


### -field LinkUsagePage

Specifies the <a href="hid.hid_usages#usage_page#usage_page">usage page</a> of the collection.


### -field Parent

Specifies the index of the collection's parent collection. If the collection has no parent, <b>Parent</b> is zero.


### -field NumberOfChildren

Specifies the number of child collections that the collection contains.


### -field NextSibling

Specifies the index of the collection's immediate sibling. If the collection has no sibling, <b>NextSibling</b> is zero.


### -field FirstChild

Specifies the index of the collection's first child collection. If the collection has no children, <b>FirstChild</b> is zero.


### -field CollectionType

Specifies the type of collection item.


### -field IsAlias

Specifies, if <b>TRUE</b>, that this collection is an <a href="hid.link_collections#aliased_collections#aliased_collections">aliased collection</a>. Otherwise, if <b>FALSE</b>, the collection is not aliased.


### -field Reserved

Reserved for internal system use.


### -field UserContext

Pointer to application-specific information.


## -remarks
The <a href="hid.hidp_getlinkcollectionnodes">HidP_GetLinkCollectionNodes</a> routine returns a top-level collection's link collection array. The indices specified in a link collection node are indices in the collection's link collection array.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidpi.h (include Hidpi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.hidp_getlinkcollectionnodes">HidP_GetLinkCollectionNodes</a>
</dt>
<dt>
<a href="hid.hidp_button_caps">HIDP_BUTTON_CAPS</a>
</dt>
<dt>
<a href="hid.hidp_value_caps">HIDP_VALUE_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_LINK_COLLECTION_NODE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

