---
UID: NS.HIDPI._HIDP_CAPS
title: _HIDP_CAPS
author: windows-driver-content
description: The HIDP_CAPS structure contains information about a top-level collection's capability.
old-location: hid\hidp_caps.htm
old-project: hid
ms.assetid: ec4d4b7b-acf6-4839-9a61-1883eddce3f4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HIDP_CAPS, PHIDP_CAPS, *PHIDP_CAPS, HIDP_CAPS
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
req.alt-api: HIDP_CAPS
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

# _HIDP_CAPS structure



## -description
The HIDP_CAPS structure contains information about a top-level <a href="https://msdn.microsoft.com/228fab4f-ff90-43c5-bc68-26b29e8a7dd6">collection's capability</a>.



## -syntax

````
typedef struct _HIDP_CAPS {
  USAGE  Usage;
  USAGE  UsagePage;
  USHORT InputReportByteLength;
  USHORT OutputReportByteLength;
  USHORT FeatureReportByteLength;
  USHORT Reserved[17];
  USHORT NumberLinkCollectionNodes;
  USHORT NumberInputButtonCaps;
  USHORT NumberInputValueCaps;
  USHORT NumberInputDataIndices;
  USHORT NumberOutputButtonCaps;
  USHORT NumberOutputValueCaps;
  USHORT NumberOutputDataIndices;
  USHORT NumberFeatureButtonCaps;
  USHORT NumberFeatureValueCaps;
  USHORT NumberFeatureDataIndices;
} HIDP_CAPS, *PHIDP_CAPS;
````


## -struct-fields

### -field Usage

Specifies a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="hid.hid_usages#usage_id#usage_id">usage ID</a>.


### -field UsagePage

Specifies the top-level collection's <a href="hid.hid_usages#usage_page#usage_page">usage page</a>.


### -field InputReportByteLength

Specifies the maximum size, in bytes, of all the input reports (including the report ID, if report IDs are used, which is prepended to the report data).


### -field OutputReportByteLength

Specifies the maximum size, in bytes, of all the output reports (including the report ID, if report IDs are used, which is prepended to the report data).


### -field FeatureReportByteLength

Specifies the maximum length, in bytes, of all the feature reports (including the report ID, if report IDs are used, which is prepended to the report data).


### -field Reserved

Reserved for internal system use.


### -field NumberLinkCollectionNodes

Specifies the number of <a href="hid.hidp_link_collection_node">HIDP_LINK_COLLECTION_NODE</a> structures that are returned for this top-level collection by <a href="hid.hidp_getlinkcollectionnodes">HidP_GetLinkCollectionNodes</a>.


### -field NumberInputButtonCaps

Specifies the number of input <a href="hid.hidp_button_caps">HIDP_BUTTON_CAPS</a> structures that <a href="hid.hidp_getbuttoncaps">HidP_GetButtonCaps</a> returns.


### -field NumberInputValueCaps

Specifies the number of input <a href="hid.hidp_value_caps">HIDP_VALUE_CAPS</a> structures that <a href="hid.hidp_getvaluecaps">HidP_GetValueCaps</a> returns.


### -field NumberInputDataIndices

Specifies the number of <a href="https://msdn.microsoft.com/84577544-515a-4fdc-86e5-518182c6c461">data indices</a> assigned to buttons and values in all input reports.


### -field NumberOutputButtonCaps

Specifies the number of output HIDP_BUTTON_CAPS structures that <b>HidP_GetButtonCaps</b> returns.


### -field NumberOutputValueCaps

Specifies the number of output HIDP_VALUE_CAPS structures that <b>HidP_GetValueCaps</b> returns.


### -field NumberOutputDataIndices

Specifies the number of data indices assigned to buttons and values in all output reports.


### -field NumberFeatureButtonCaps

Specifies the total number of feature HIDP_BUTTONS_CAPS structures that <b>HidP_GetButtonCaps</b> returns.


### -field NumberFeatureValueCaps

Specifies the total number of feature HIDP_VALUE_CAPS structures that <b>HidP_GetValueCaps</b> returns.


### -field NumberFeatureDataIndices

Specifies the number of data indices assigned to buttons and values in all feature reports.


## -remarks
Callers of the <a href="hid.hidclass_support_routines">HIDClass support routines</a> use the information provided in this structure when a called routine requires, as input, the size of a report type, the number of link collection nodes, the number of control capabilities, or the number of data indices.


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
<a href="hid.hidp_getcaps">HidP_GetCaps</a>
</dt>
<dt>
<a href="hid.hidp_getbuttoncaps">HidP_GetButtonCaps</a>
</dt>
<dt>
<a href="hid.hidp_getlinkcollectionnodes">HidP_GetLinkCollectionNodes</a>
</dt>
<dt>
<a href="hid.hidp_getspecificbuttoncaps">HidP_GetSpecificButtonCaps</a>
</dt>
<dt>
<a href="hid.hidp_getspecificvaluecaps">HidP_GetSpecificValueCaps</a>
</dt>
<dt>
<a href="hid.hidp_getvaluecaps">HidP_GetValueCaps</a>
</dt>
<dt>
<a href="hid.hidp_link_collection_node">HIDP_LINK_COLLECTION_NODE</a>
</dt>
<dt>
<a href="hid.hidp_button_caps">HIDP_BUTTON_CAPS</a>
</dt>
<dt>
<a href="hid.hidp_value_caps">HIDP_VALUE_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_CAPS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

