---
UID: NN.printerextension.IPrinterBidiSetRequestCallback
title: IPrinterBidiSetRequestCallback
author: windows-driver-content
description: Describes the signature of the callback object that receives the Bidi response.
old-location: print\iprinterbidisetrequestcallback.htm
old-project: print
ms.assetid: C85690D0-3CA7-46C7-B597-E36555879F08
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: tagPrintSchemaSelectionType, PrintSchemaSelectionType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterBidiSetRequestCallback
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IPrinterBidiSetRequestCallback interface



## -description
Describes the signature of the callback object that receives the Bidi response.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterBidiSetRequestCallback</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPrinterBidiSetRequestCallback</b> also has these types of members:

The <b>IPrinterBidiSetRequestCallback</b> interface has these methods.

Invoked when the Bidi “Set”” operation is completed.

 

## -members
The <b>IPrinterBidiSetRequestCallback</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprinterbidisetrequestcallback_completed">Completed</a>
</td>
<td align="left" width="63%">
Invoked when the Bidi “Set”” operation is completed.
</td>
</tr>
</table>Invoked when the Bidi “Set”” operation is completed.

 

## -remarks
<b>IPrinterBidiSetRequestCallback</b> provides the Bidi response string, and <b>HRESULT</b> value returned from the <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd144984(v=vs.85).aspx">IBidiSpl2::SendRecvXmlString</a> method. In other words,  this interface provides the results of the attempt to send data to the device. 

<b>IPrinterBidiSetRequestCallback</b>  helps to make it possible to perform device maintenance from a UWP  device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>
</dt>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd144984(v=vs.85).aspx">IBidiSpl2::SendRecvXmlString</a></dt>
<dt>
<a href="print.iprinterqueue2_sendbidisetrequestasync">SendBidiSetRequestAsync</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterBidiSetRequestCallback interface%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
