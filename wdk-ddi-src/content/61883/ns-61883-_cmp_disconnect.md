---
UID: NS.61883._CMP_DISCONNECT
title: _CMP_DISCONNECT
author: windows-driver-content
description: This structure is used to break a connection.
old-location: ieee\cmp_disconnect.htm
old-project: IEEE
ms.assetid: 7EAE617D-EFF9-4F77-9B9C-5985B864B310
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _CMP_DISCONNECT, *PCMP_DISCONNECT, PCMP_DISCONNECT, CMP_DISCONNECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CMP_DISCONNECT
req.alt-loc: 61883.h
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

# _CMP_DISCONNECT structure



## -description
This structure is used to break a connection. 



## -syntax

````
typedef struct _CMP_DISCONNECT {
  HANDLE hConnect;
} CMP_DISCONNECT, *PCMP_DISCONNECT;
````


## -struct-fields

### -field hConnect

On input, a handle to the connection to break.


## -remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>61883.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_DISCONNECT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

