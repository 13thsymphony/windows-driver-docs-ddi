---
UID: NS.HBAPIWMI._GETPORTATTRIBUTESBYWWN_IN
title: _GetPortAttributesByWWN_IN
author: windows-driver-content
description: The GetPortAttributesByWWN_IN structure is used by a WMI client to deliver input parameter data to the GetPortAttributesByWWN WMI method.
old-location: storage\getportattributesbywwn_in.htm
old-project: storage
ms.assetid: 2b189ece-6c49-42e2-8ef2-b3db516fc844
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _GetPortAttributesByWWN_IN, *PGetPortAttributesByWWN_IN, GetPortAttributesByWWN_IN
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
req.alt-api: GetPortAttributesByWWN_IN
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

# _GetPortAttributesByWWN_IN structure



## -description
The GetPortAttributesByWWN_IN structure is used by a WMI client to deliver input parameter data to the <a href="storage.getportattributesbywwn">GetPortAttributesByWWN</a> WMI method. 



## -syntax

````
typedef struct _GetPortAttributesByWWN_IN {
  UCHAR wwn[8];
} GetPortAttributesByWWN_IN, *PGetPortAttributesByWWN_IN;
````


## -struct-fields

### -field wwn

Contains a worldwide name that identifies a port of type FC_Port.


## -remarks
The WMI tool suite generates a declaration of the GetPortAttributesByWWN_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.

For a definition of FC_Port and a discussion of worldwide names, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).


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
<a href="storage.getportattributesbywwn">GetPortAttributesByWWN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetPortAttributesByWWN_IN structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

