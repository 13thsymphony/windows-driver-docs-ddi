---
UID: NF.wiautil.wiauDbgLegacyHresult2
title: wiauDbgLegacyHresult2 function
author: windows-driver-content
description: The wiauDbgLegacyHresult2 function logs a default message containing an HRESULT.
old-location: image\wiaudbglegacyhresult2.htm
old-project: image
ms.assetid: 1b73c94b-07a8-4b65-8ed7-d5f1a073c3b2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiauDbgLegacyHresult2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiauDbgLegacyHresult2
req.alt-loc: wiautil.h
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
req.product: Windows 10 or later.
---

# wiauDbgLegacyHresult2 function



## -description
The <b>wiauDbgLegacyHresult2</b> function logs a default message containing an HRESULT.



## -syntax

````
inline void __stdcall wiauDbgLegacyHresult2(
  _In_ HINSTANCE hInstance,
       HRESULT   hr
);
````


## -parameters

### -param hInstance [in]

Specifies the handle to the DLL instance.


### -param hr 

Specifies the HRESULT to be logged.


## -returns
None


## -remarks
A call to the <b>wiauDbgLegacyHresult2</b> function is equivalent to the following call to the <a href="image.wiaudbgerrorhr">wiauDbgErrorHr</a> function:

That is, only one line is output to the log file and/or debugger. The line has the following form:


## -requirements
<table>
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
Version

</th>
<td width="70%">
Available in Windows XP and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiautil.h (include Wiautil.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.wiaudbgerrorhr">wiauDbgErrorHr</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgLegacyHresult2 function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

