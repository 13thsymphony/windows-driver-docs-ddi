---
UID: NN.bidispl.IBidiRequest~r1
title: IBidiRequest
author: windows-driver-content
description: The IBidiRequest interface allows an application or other objects to compose a bidi request.
old-location: print\ibidirequest.htm
old-project: print
ms.assetid: e7b16853-7f1d-45e4-af5e-4ae9cbb9b191
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
req.alt-api: IBidiRequest
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

# IBidiRequest interface



## -description
The <b>IBidiRequest</b> interface allows an application or other objects to compose a bidi request.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiRequest</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IBidiRequest</b> also has these types of members:

The <b>IBidiRequest</b> interface has these methods.

Gets the number of output items.

Gets the output data coming back from the device.

Gets the result code.

Sets the data to send to the device.

Sets the bidi schema string.

 

## -members
The <b>IBidiRequest</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidirequest_ibidirequest__getenumcount">GetEnumCount</a>
</td>
<td align="left" width="63%">
Gets the number of output items.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidirequest_ibidirequest__getoutputdata">GetOutputData</a>
</td>
<td align="left" width="63%">
Gets the output data coming back from the device.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidirequest_ibidirequest__getresult">GetResult</a>
</td>
<td align="left" width="63%">
Gets the result code.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidirequest_ibidirequest__setinputdata">SetInputData</a>
</td>
<td align="left" width="63%">
Sets the data to send to the device.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ibidirequest_ibidirequest__setschema">SetSchema</a>
</td>
<td align="left" width="63%">
Sets the bidi schema string.
</td>
</tr>
</table>Gets the number of output items.

Gets the output data coming back from the device.

Gets the result code.

Sets the data to send to the device.

Sets the bidi schema string.

 

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
<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequest interface%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
