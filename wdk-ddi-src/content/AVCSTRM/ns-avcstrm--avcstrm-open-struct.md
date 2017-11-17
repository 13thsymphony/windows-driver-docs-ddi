---
UID: NS.avcstrm._AVCSTRM_OPEN_STRUCT
title: AVCSTRM_OPEN_STRUCT
author: windows-driver-content
description: The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened.
old-location: stream\avcstrm_open_struct.htm
ms.assetid: c16a2f3c-a5be-4132-920a-b81f67c5ea02
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVCSTRM_OPEN_STRUCT
req.alt-loc: avcstrm.h
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
ms.keywords: AVCSTRM_OPEN_STRUCT, AVCSTRM_OPEN_STRUCT, *PAVCSTRM_OPEN_STRUCT
req.iface: 
---

# AVCSTRM_OPEN_STRUCT structure



## -description
<p>The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened.</p>


## -syntax

````
typedef struct _AVCSTRM_OPEN_STRUCT {
  KSPIN_DATAFLOW       DataFlow;
  PAVCSTRM_FORMAT_INFO AVCFormatInfo;
  PVOID                AVCStreamContext;
  HANDLE               hPlugLocal;
} AVCSTRM_OPEN_STRUCT, *PAVCSTRM_OPEN_STRUCT;
````


## -struct-fields
<dl>

### -field <b>DataFlow</b>

<dd>
<p>Specifies the direction of the data-flow.</p>
</dd>

### -field <b>AVCFormatInfo</b>

<dd>
<p>Pointer to a description of the subunit stream format.</p>
</dd>

### -field <b>AVCStreamContext</b>

<dd>
<p>Pointer to a stream context (handle) that is passed to subsequent <i>avcstrm.sys</i> operations. Its content should not be used or altered.</p>
</dd>

### -field <b>hPlugLocal</b>

<dd>
<p>Specifies a local plug created by an AV/C subunit, which is used to connect to the target device.</p>
</dd>
</dl>

## -remarks
<p>The <b>AVCSTRM_OPEN</b> function code uses this structure to describe the open operation. If the operation is successful, a stream context (handle) is returned to the caller in the <b>AVCStrmContext </b>member of this structure, <i>not</i> the <b>AVCStrmContext</b> member in the AVC_STREAM_REQUEST_BLOCK structure.</p>

<p>This value can then be used in subsequent <i>avcstrm.sys</i> operations by placing it in the <b>AVCStrmContext</b> member of the AVC_STREAM_REQUEST_BLOCK structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Avcstrm.h (include Avcstrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554117">AVCSTRM_FORMAT_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCSTRM_OPEN_STRUCT structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
