---
UID: NS.HBAPIWMI._SENDCTPASSTHRU_IN
title: _SendCTPassThru_IN
author: windows-driver-content
description: The SendCTPassThru_IN structure is used to deliver input parameter data to the SendCTPassThru WMI method.
old-location: storage\sendctpassthru_in.htm
old-project: storage
ms.assetid: 5a3e06f5-f7f7-4e89-b78e-d6658c34ba9e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SendCTPassThru_IN, *PSendCTPassThru_IN, PSendCTPassThru_IN, SendCTPassThru_IN
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
req.alt-api: SendCTPassThru_IN
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

# _SendCTPassThru_IN structure



## -description
The SendCTPassThru_IN structure is used to deliver input parameter data to the <a href="storage.sendctpassthru">SendCTPassThru</a> WMI method. 



## -syntax

````
typedef struct _SendCTPassThru_IN {
  UCHAR PortWWN[8];
  ULONG RequestBufferCount;
  UCHAR RequestBuffer[1];
} SendCTPassThru_IN, *PSendCTPassThru_IN;
````


## -struct-fields

### -field PortWWN

Contains a worldwide name for the HBA through which the target is accessed. 


### -field RequestBufferCount

Indicates the size in bytes of the buffer that will hold the results of the common transport command. 


### -field RequestBuffer

Contains the results of the common transport command. 


## -remarks
The WMI tool suite generates a declaration of the SendCTPassThru_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.


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
<a href="storage.sendctpassthru">SendCTPassThru</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendCTPassThru_IN structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

