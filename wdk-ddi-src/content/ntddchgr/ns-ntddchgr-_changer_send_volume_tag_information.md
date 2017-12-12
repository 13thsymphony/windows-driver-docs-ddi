---
UID: NS.NTDDCHGR._CHANGER_SEND_VOLUME_TAG_INFORMATION
title: _CHANGER_SEND_VOLUME_TAG_INFORMATION
author: windows-driver-content
description: This structure is passed to the ChangerQueryVolumeTags routine and is used to specify a search criterion for retrieving changer elements.
old-location: storage\changer_send_volume_tag_information.htm
old-project: storage
ms.assetid: cfe0673c-1dcb-4c4e-9ec4-8d9f27919c85
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _CHANGER_SEND_VOLUME_TAG_INFORMATION, CHANGER_SEND_VOLUME_TAG_INFORMATION, *PCHANGER_SEND_VOLUME_TAG_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CHANGER_SEND_VOLUME_TAG_INFORMATION
req.alt-loc: ntddchgr.h
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
---

# _CHANGER_SEND_VOLUME_TAG_INFORMATION structure



## -description
This structure is passed to the <a href="storage.changerqueryvolumetags">ChangerQueryVolumeTags</a> routine and is used to specify a search criterion for retrieving changer elements. 



## -syntax

````
typedef struct _CHANGER_SEND_VOLUME_TAG_INFORMATION {
  CHANGER_ELEMENT StartingElement;
  ULONG           ActionCode;
  UCHAR           VolumeIDTemplate[MAX_VOLUME_TEMPLATE_SIZE];
} CHANGER_SEND_VOLUME_TAG_INFORMATION, *PCHANGER_SEND_VOLUME_TAG_INFORMATION;
````


## -struct-fields

### -field StartingElement

Describes the first element of the range to search for or to set in a structure of type <a href="storage.changer_element">CHANGER_ELEMENT</a>. 


### -field ActionCode

Indicates the operation to perform. The <b>Features0</b> member of <a href="storage.get_changer_parameters">GET_CHANGER_PARAMETERS</a> indicates whether the changer supports a particular category of operation:

<ul>
<li>
Translate operations, also known as "searching operations", request that the target device search its volume tag information for elements that match the template passed to the device. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_SEARCH.

</li>
<li>
Assert operations define volume tag information for a single element. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_ASSERT.

</li>
<li>
Replace operations define volume tag information for a single element, overwriting any information previously defined. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_REPLACE. 

</li>
<li>
Undefined operations clear previously defined volume tag information for a single element. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_UNDEFINE. 

</li>
</ul>

### -field VolumeIDTemplate

Specifies the template to be used by the device to search for volume IDs. For a translate operation, the template can include the wildcard characters, asterisk (*) and question mark (?), to search for volumes that match the template. For other operations, the template specifies a single volume. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddchgr.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.read_element_address_info">READ_ELEMENT_ADDRESS_INFO</a>
</dt>
<dt>
<a href="storage.get_changer_parameters">GET_CHANGER_PARAMETERS</a>
</dt>
<dt>
<a href="storage.changerqueryvolumetags">ChangerQueryVolumeTags</a>
</dt>
<dt>
<a href="storage.changer_element">CHANGER_ELEMENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_SEND_VOLUME_TAG_INFORMATION structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

