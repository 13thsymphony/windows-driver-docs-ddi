---
UID: NF.scsiwmi.ScsiPortWmiPostProcess
title: ScsiPortWmiPostProcess
author: windows-driver-content
description: The ScsiPortWmiPostProcess routine updates a request context for a WMI SRB.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwmipostprocess.htm
ms.assetid: da1770bc-2233-47ef-afab-cfcb34edb4b9
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortWmiPostProcess
req.alt-loc: scsiwmi.h
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
ms.keywords: ScsiPortWmiPostProcess
req.iface: 
req.product: Windows 10 or later.
---

# ScsiPortWmiPostProcess function



## -description
<p>The <b>ScsiPortWmiPostProcess</b> routine updates a request context for a WMI SRB.</p>


## -syntax

````
VOID ScsiPortWmiPostProcess(
  _In_ PSCSIWMI_REQUEST_CONTEXT RequestContext,
  _In_ UCHAR                    SrbStatus,
  _In_ ULONG                    BufferUsed
);
````


## -parameters
<dl>

### -param <i>RequestContext</i> [in]

<dd>
<p>A pointer to the request context for this SRB.</p>
</dd>

### -param <i>SrbStatus</i> [in]

<dd>
<p>Specifies any valid SRB status. If the output buffer passed to the miniport driver was too small to contain all of the data from a request, the miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN.</p>
</dd>

### -param <i>BufferUsed</i> [in]

<dd>
<p>If <i>SrbStatus</i> indicates success, the miniport driver sets <i>BufferUsed</i> to the number of bytes of data written to the buffer. If <i>SrbStatus</i> is SRB_STATUS_DATA_OVERRUN, the miniport driver sets <i>BufferUsed</i> to the number of bytes required to complete the SRB successfully.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A miniport driver must call <b>ScsiPortWmiPostProcess</b> after the WMI SRB request has been processed and is ready to be completed.</p>

<p>For synchronous SRBs, <b>ScsiPortWmiPostProcess</b> is called in the callback routine.</p>

<p>For pending SRBs, <b>ScsiPortWmiPostProcess</b> is called after the SRB has been processed, and before it is completed.</p>

<p>If a miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN and sets <i>BufferUsed</i>, successive identical WMI SRBs with an allocated buffer equal to or greater than <i>BufferUsed</i> bytes should succeed. This should be achieved if the driver sets the exact value for <i>BufferUsed</i> that is needed to complete the request when calling <b>ScsiPortWmiPostProcess</b> with <i>SrbStatus</i> equal to SRB_STATUS_DATA_OVERRUN. For a variable-sized output structure, the input data buffer of the SRB should have enough information to determine the exact <i>BufferUsed</i> value. If the input data buffer does not contain enough information, the driver should never fail the same SRB two times with SRB_STATUS_DATA_OVERRUN. Instead, the driver should set SRB_STATUS_DATA_OVERRUN and request the minimum size necessary for the output buffer first, and then set SRB_STATUS_SUCCESS and indicate the failure in the contents of the output buffer.</p>

<p>A miniport driver must call <b>ScsiPortWmiPostProcess</b> after the WMI SRB request has been processed and is ready to be completed.</p>

<p>For synchronous SRBs, <b>ScsiPortWmiPostProcess</b> is called in the callback routine.</p>

<p>For pending SRBs, <b>ScsiPortWmiPostProcess</b> is called after the SRB has been processed, and before it is completed.</p>

<p>If a miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN and sets <i>BufferUsed</i>, successive identical WMI SRBs with an allocated buffer equal to or greater than <i>BufferUsed</i> bytes should succeed. This should be achieved if the driver sets the exact value for <i>BufferUsed</i> that is needed to complete the request when calling <b>ScsiPortWmiPostProcess</b> with <i>SrbStatus</i> equal to SRB_STATUS_DATA_OVERRUN. For a variable-sized output structure, the input data buffer of the SRB should have enough information to determine the exact <i>BufferUsed</i> value. If the input data buffer does not contain enough information, the driver should never fail the same SRB two times with SRB_STATUS_DATA_OVERRUN. Instead, the driver should set SRB_STATUS_DATA_OVERRUN and request the minimum size necessary for the output buffer first, and then set SRB_STATUS_SUCCESS and indicate the failure in the contents of the output buffer.</p>

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
<dt>Scsiwmi.h (include Miniport.h or Scsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564789">ScsiPortWmiGetReturnSize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564946">SCSIWMI_REQUEST_CONTEXT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20ScsiPortWmiPostProcess routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
