---
UID: NS.61883._CMP_CONNECT_VER2
title: CMP_CONNECT_VER2
author: windows-driver-content
description: This structure contains information for a connection request. The request attempts to make a connection to a plug control register on the local host.
old-location: ieee\cmp_connect_ver2.htm
old-project: IEEE
ms.assetid: 2A2C1478-0512-4F84-90B9-B9C62B5D44DA
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: CMP_CONNECT_VER2, CMP_CONNECT_VER2, *PCMP_CONNECT_VER2
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

# CMP_CONNECT_VER2 structure



## -description
<p>This structure contains information for a connection request. The  request attempts to make a connection to a plug control register on the local host.</p>


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
<dl>

### -field hOutputPlug

<dd>
<p>On input, a handle to the output plug to use for the connection. If <b>hOutputPlug</b> is <b>NULL</b>, the connection is for input only.</p>
</dd>

### -field hInputPlug

<dd>
<p>On input, handle to the input plug to use for the connection. If <b>hInputPlug</b> is <b>NULL</b>, the connection is for output only.</p>
</dd>

### -field Type

<dd>
<p>On input, the type of the requested connection.</p>
<p>The type of connection to make. Can be one of the following:</p>
<p></p>
<dl>

### -field CMP_Broadcast

<dd>
<p>A broadcast connection.  </p>
</dd>

### -field CMP_PointToPoint

<dd>
<p>A connection between a single output plug and one or more input plugs. </p>
</dd>
</dl>
</dd>

### -field Format

<dd>
<p>The requested data format.</p>
<p>On input, a pointer to a <a href="..\61883\ns-61883--cip-data-format-ver2.md">CIP_DATA_FORMAT_VER2</a> structure that specifies the format of the connection.</p>
</dd>

### -field hConnect

<dd>
<p>On output, the handle for the created connection.</p>
</dd>
</dl>

## -remarks
<p>If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. </p>

<p>If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.</p>

<p>If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\ieee]:%20CMP_CONNECT_VER2 structure%20 RELEASE:%20(11/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
