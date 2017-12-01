---
UID: NF.hbaapi.HBA_SendRNIDV2
title: HBA_SendRNIDV2
author: windows-driver-content
description: The HBA_SendRNIDV2 routine sends a request for node identification data (RNID) to the indicated HBA, which in turn routes the request through the indicated port or node to the appropriate fabric configuration server.
old-location: storage\hba_sendrnidv2.htm
old-project: storage
ms.assetid: c46aee6e-f31d-4b8d-8244-3c364aa79ae4
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_SendRNIDV2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_SendRNIDV2
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
req.iface: 
---

# HBA_SendRNIDV2 function



## -description
<p>The <b>HBA_SendRNIDV2</b> routine sends a request for node identification data (RNID) to the indicated HBA, which in turn routes the request through the indicated port or node to the appropriate fabric configuration server. </p>


## -syntax

````
HBA_STATUS HBA_API HBA_SendRNIDV2(
  _In_    HBA_HANDLE handle,
  _In_    HBA_WWN    hbaPortWWN,
  _In_    HBA_WWN    destWWN,
  _In_    HBA_UINT32 destFCID,
  _In_    HBA_UINT32 NodeIdDataFormat,
  _Out_   void       *pRspBuffer,
  _Inout_ HBA_UINT32 *RspBufferSize
);
````


## -parameters
<dl>

### -param <i>handle</i> [in]

<dd>
<p>Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba-openadapter.md">HBA_OpenAdapter</a> that identifies the HBA that will route the command. The HBA routes this command through the port specified by <i>hbaPortWWN </i>to the port specified by <i>destWWN </i>on the appropriate fabric configuration server. </p>
</dd>

### -param <i>hbaPortWWN</i> [in]

<dd>
<p>Contains a 64-bit worldwide name (WWN) that uniquely identifies a port from which the RNID command is issued. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. </p>
</dd>

### -param <i>destWWN</i> [in]

<dd>
<p>Contains a WWN for the destination port on the fabric configuration server that will provide the node identification data. </p>
</dd>

### -param <i>destFCID</i> [in]

<dd>
<p>Contains the fibre channel identifier of the destination port specified by <i>destWWN. </i>If no fibre channel identifier for the destination port is available, the caller should set this member to 0. </p>
</dd>

### -param <i>NodeIdDataFormat</i> [in]

<dd>
<p>Contains a number that indicates the node identification format. For a complete description of the allowed formats and the numbers that identify each format, see the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee.</p>
</dd>

### -param <i>pRspBuffer</i> [out]

<dd>
<p>Pointer to a buffer that contains the payload data, in big-endian (wire) format, from the reply to the node identification request.  </p>
</dd>

### -param <i>RspBufferSize</i> [in, out]

<dd>
<p>On input, indicates the size, in bytes, of the buffer pointed to by <i>pRspBuffer</i>. On return, this member indicates the size, in bytes, of the response data. </p>
</dd>
</dl>

## -returns
<p>The <b>HBA_SendRNIDV2</b> routine returns a value of type <a href="storage.hba_status">HBA_STATUS</a> that indicates the status of the HBA.</p>

## -remarks
<p>The node identification data request is a common transport (CT) command that queries a fabric configuration server for node identification data. For a complete description of this command, see the sections dealing with node identification requests in the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee.</p>

<p>The <b>HBA_SendRNIDV2</b> library routine serves a purpose very similar to the <a href="storage.sendrnid">SendRNID</a> WMI method. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba-openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba-sendrnid.md">HBA_SendRNID</a>
</dt>
<dt>
<a href="storage.sendrnid">SendRNID</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendRNIDV2 routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
