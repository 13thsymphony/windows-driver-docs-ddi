---
UID: NS.HIDPDDI._HIDP_DEVICE_DESC
title: _HIDP_DEVICE_DESC
author: windows-driver-content
description: Contains the device description block filled in collection descriptions as linked lists. This structure is used by HidP_GetCollectionDescription.
old-location: hid\hidp_device_desc.htm
old-project: hid
ms.assetid: C51D645B-5DF2-4F23-904B-AB56F97520CB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HIDP_DEVICE_DESC, HIDP_DEVICE_DESC, *PHIDP_DEVICE_DESC, PHIDP_DEVICE_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpddi.h
req.include-header: Hidpddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HIDP_DEVICE_DESC
req.alt-loc: Hidpddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# _HIDP_DEVICE_DESC structure



## -description
Contains the device description block filled in
                         collection descriptions as linked lists. This structure is used by <a href="hid.hidp_getcollectiondescription">HidP_GetCollectionDescription</a>.



## -syntax

````
typedef struct _HIDP_DEVICE_DESC {
  PHIDP_COLLECTION_DESC     CollectionDesc;
  ULONG                     CollectionDescLength;
  PHIDP_REPORT_IDS          ReportIDs;
  ULONG                     ReportIDsLength;
  HIDP_GETCOLDESC_DBG       Dbg;
} HIDP_DEVICE_DESC, *PHIDP_DEVICE_DESC;
````


## -struct-fields

### -field CollectionDesc

An array of  <a href="hid.hidp_collection_desc">HIDP_COLLECTION_DESC</a> structure that contains the collection descriptors.


### -field CollectionDescLength

The number of elements in the array of the collection descriptors.


### -field ReportIDs

An array of <a href="hid.hidp_report_ids">HIDP_REPORT_IDS</a> structures report ID information for a report descriptor. 


### -field ReportIDsLength

The number of elements in the length of the array of report IDs.


### -field Dbg

A <a href="hid.hidp_getcoldesc_dbg">HIDP_GETCOLDESC_DBG</a> structure that contains the error code indicating the failure in parsing the report 
                                      descriptor.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidpddi.h (include Hidpddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.hidp_getcollectiondescription">HidP_GetCollectionDescription</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_DEVICE_DESC structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

