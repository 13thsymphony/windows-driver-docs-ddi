---
UID: NS.61883._CMP_CONNECT_VER2
title: _CMP_CONNECT_VER2
author: windows-driver-content
description: This structure contains information for a connection request. The request attempts to make a connection to a plug control register on the local host.
old-location: ieee\cmp_connect_ver2.htm
old-project: IEEE
ms.assetid: 2A2C1478-0512-4F84-90B9-B9C62B5D44DA
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _CMP_CONNECT_VER2, *PCMP_CONNECT_VER2, CMP_CONNECT_VER2
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
req.alt-api: CMP_CONNECT_VER2
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

# _CMP_CONNECT_VER2 structure



## -description
This structure contains information for a connection request. The  request attempts to make a connection to a plug control register on the local host.



## -syntax

````
typedef struct _CMP_CONNECT_VER2 {
  HANDLE               hOutputPlug;
  HANDLE               hInputPlug;
  CMP_CONNECT_TYPE     Type;
  CIP_DATA_FORMAT_VER2 Format;
  HANDLE               hConnect;
} CMP_CONNECT_VER2, *PCMP_CONNECT_VER2;
````


## -struct-fields

### -field hOutputPlug

On input, a handle to the output plug to use for the connection. If <b>hOutputPlug</b> is <b>NULL</b>, the connection is for input only.


### -field hInputPlug

On input, handle to the input plug to use for the connection. If <b>hInputPlug</b> is <b>NULL</b>, the connection is for output only.


### -field Type

On input, the type of the requested connection.

The type of connection to make. Can be one of the following:




### -field CMP_Broadcast

A broadcast connection.  


### -field CMP_PointToPoint

A connection between a single output plug and one or more input plugs. 

</dd>
</dl>

### -field Format

The requested data format.

On input, a pointer to a <a href="ieee.cip_data_format_ver2">CIP_DATA_FORMAT_VER2</a> structure that specifies the format of the connection.


### -field hConnect

On output, the handle for the created connection.


## -remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\ieee]:%20CMP_CONNECT_VER2 structure%20 RELEASE:%20(11/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

