---
UID: NS.ISCSIOP._SCSIINQUIRY_IN
title: _ScsiInquiry_IN
author: windows-driver-content
description: The ScsiInquiry_IN structure holds the input data for the ScsiInquiry method, which is used to send a SCSI inquiry command.
old-location: storage\scsiinquiry_in.htm
old-project: storage
ms.assetid: b1a73ef7-c13a-4627-8eb0-b9285567caec
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _ScsiInquiry_IN, PScsiInquiry_IN, ScsiInquiry_IN, *PScsiInquiry_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiInquiry_IN
req.alt-loc: iscsiop.h
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

# _ScsiInquiry_IN structure



## -description
The ScsiInquiry_IN structure holds the input data for the <a href="storage.scsiinquiry">ScsiInquiry</a> method, which is used to send a SCSI inquiry command.



## -syntax

````
typedef struct _ScsiInquiry_IN {
  ULONGLONG UniqueSessionId;
  ULONGLONG Lun;
  UCHAR     InquiryFlags;
  UCHAR     PageCode;
} ScsiInquiry_IN, *PScsiInquiry_IN;
````


## -struct-fields

### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="storage.logintotarget">LoginToTarget</a> and <a href="storage.addconnectiontosession">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field Lun

A 64-bit number that, together with the name of the target, uniquely identifies the logical unit.


### -field InquiryFlags

The inquiry flags to set in the SCSI inquiry command. A value of 1 in the lowest order bit (0x01) indicates that the enable vital product data (EVPD) bit will be set in the inquiry command and the device server will return the optional vital product data that the page code field specifies in the inquiry command. A value of 1 in the second bit (0x02) indicates that the command support data bit will be set in the inquiry command and the device server will return the optional command support data that the operation code field specifies in the inquiry command.


### -field PageCode

The page code field in the SCSI inquiry command.


## -remarks
You must implement this method.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.addconnectiontosession">AddConnectionToSession</a>
</dt>
<dt>
<a href="storage.logintotarget">LoginToTarget</a>
</dt>
<dt>
<a href="storage.scsiinquiry">ScsiInquiry</a>
</dt>
<dt>
<a href="storage.scsiinquiry_out">ScsiInquiry_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiInquiry_IN structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

