---
UID: NS.HBAPIWMI._MSFC_FIBREPORTHBAATTRIBUTES
title: _MSFC_FibrePortHBAAttributes
author: windows-driver-content
description: A WMI provider uses the MSFC_FibrePortHBAAttributes WMI class to expose attribute information associated with a fibre channel port.
old-location: storage\msfc_fibreporthbaattributes.htm
old-project: storage
ms.assetid: e8a31f48-bad2-49d1-81be-d345d87a0fd5
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MSFC_FibrePortHBAAttributes, *PMSFC_FibrePortHBAAttributes, PMSFC_FibrePortHBAAttributes, MSFC_FibrePortHBAAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSFC_FibrePortHBAAttributes
req.alt-loc: hbapiwmi.h
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

# _MSFC_FibrePortHBAAttributes structure



## -description
A WMI provider uses the MSFC_FibrePortHBAAttributes WMI class to expose attribute information associated with a fibre channel port.



## -syntax

````
typedef struct _MSFC_FibrePortHBAAttributes {
  ULONGLONG                     UniquePortId;
  ULONG                         HBAStatus;
  MSFC_HBAPortAttributesResults Attributes;
} MSFC_FibrePortHBAAttributes, *PMSFC_FibrePortHBAAttributes;
````


## -struct-fields

### -field UniquePortId

Unique identifier for the port. This identifier must be unique among all ports on all adapters. The same value for the identifier must be used for the same port in other classes that expose port information.


### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.


### -field Attributes

Contains a structure of type <a href="storage.msfc_hbaportattributesresults">MSFC_HBAPortAttributesResults</a> that contains information about the port attributes. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
<dt>
<a href="storage.msfc_hbaportattributesresults">MSFC_HBAPortAttributesResults</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_FibrePortHBAAttributes structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
