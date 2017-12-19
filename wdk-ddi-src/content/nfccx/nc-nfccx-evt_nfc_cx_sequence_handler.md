---
UID: NC.nfccx.EVT_NFC_CX_SEQUENCE_HANDLER
title: EVT_NFC_CX_SEQUENCE_HANDLER
author: windows-driver-content
description: Called by the NFC CX to notify the client driver to handle the specific registered sequence.
old-location: nfpdrivers\evtnfccxsequencehandler.htm
old-project: nfpdrivers
ms.assetid: 6EB96A37-06B9-4655-AD69-375EE770F4DF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NPI_REGISTRATION_INSTANCE, NPI_REGISTRATION_INSTANCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtNfcCxSequenceHandler
req.alt-loc: nfccx.h
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

# EVT_NFC_CX_SEQUENCE_HANDLER callback



## -description
Called by the NFC CX to notify the client driver to handle the specific registered sequence.



## -prototype

````
EVT_NFC_CX_SEQUENCE_HANDLER  EvtNfcCxSequenceHandler;

VOID  EvtNfcCxSequenceHandler(
  _In_     WDFDEVICE                              Device,
  _In_     NFC_CX_SEQUENCE                        Sequence,
  _In_     PFN_NFC_CX_SEQUENCE_COMPLETION_ROUTINE CompletionRoutine,
  _In_opt_ WDFCONTEXT                             CompletionContext
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Sequence [in]

An <a href="nfpdrivers.nfc_cx_sequence">NFC_CX_SEQUENCE</a> enumeration.


### -param CompletionRoutine [in]

A pointer to a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function.


### -param CompletionContext [in, optional]

Driver-defined context information that the driver specified when it registered the <i>EvtNfcCxSequenceHandler</i> callback function.


## -returns
None.


## -remarks
On completion of handling the sequence, the client driver notifies the NFC CX through the sequence completion callback. Similar to <a href="..\nfccx\nc-nfccx-evt_nfc_cx_write_nci_packet.md">EvtNfcCxWriteNciPacket</a>, the client must not make any blocking calls when handling this function call. Any I/O processing must be handled on a separate thread or work item. However, the client driver can invoke the completion routine with a status flag when handling this call.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Nfccx.h (include Ncidef.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20EVT_NFC_CX_SEQUENCE_HANDLER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

