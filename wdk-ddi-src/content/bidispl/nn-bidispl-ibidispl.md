---
UID: NN.bidispl.IBidiSpl
title: IBidiSpl
author: windows-driver-content
description: The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests.
old-location: print\ibidispl.htm
old-project: print
ms.assetid: 7e4a30b2-ac3a-475a-b818-455cdb7a91bf
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: _MPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: bidispl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IBidiSpl
req.alt-loc: Bidispl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IBidiSpl interface



## -description
The <b>IBidiSpl</b> interface allows an application or other objects to send a single bidi request or a list of bidi requests.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiSpl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IBidiSpl</b> also has these types of members:

The <b>IBidiSpl</b> interface has these methods.

Binds a printer to a bidi request.

Sends a list of bidi requests.

Sends a bidi request.

Unbinds a printer.

 

## -members
The <b>IBidiSpl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidispl_ibidispl__binddevice">BindDevice</a>
</td>
<td align="left" width="63%">
Binds a printer to a bidi request.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidispl_ibidispl__multisendrecv">MultiSendRecv</a>
</td>
<td align="left" width="63%">
Sends a list of bidi requests.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidispl_ibidispl__sendrecv">SendRecv</a>
</td>
<td align="left" width="63%">
Sends a bidi request.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidispl_ibidispl__unbinddevice">UnbindDevice</a>
</td>
<td align="left" width="63%">
Unbinds a printer.
</td>
</tr>
</table>Binds a printer to a bidi request.

Sends a list of bidi requests.

Sends a bidi request.

Unbinds a printer.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows XP
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2003
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bidispl.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.bidirectional_communication_interfaces">Bidirectional Communication Interfaces</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>
</dt>
<dt>
<a href="..\bidispl\nn-bidispl-ibidirequestcontainer.md">IBidiSpl</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiSpl interface%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
