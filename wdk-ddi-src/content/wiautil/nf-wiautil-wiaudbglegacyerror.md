---
UID: NF.wiautil.wiauDbgLegacyError
title: wiauDbgLegacyError function
author: windows-driver-content
description: The wiauDbgLegacyError function logs an error message.
old-location: image\wiaudbglegacyerror.htm
old-project: image
ms.assetid: c2a9bd35-ce3a-4640-9982-b470e98b4692
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiauDbgLegacyError
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
req.alt-api: wiauDbgLegacyError
req.alt-loc: Wiautil.h
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

# wiauDbgLegacyError function



## -description
The <b>wiauDbgLegacyError</b> function logs an error message.



## -syntax

````
inline void __stdcall wiauDbgLegacyError(
   LPCSTR   fmt, ...
);
````


## -parameters

### -param fmt, ... 

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns
None


## -remarks
The <b>wiauDbgLegacyError</b> function is identical to the <a href="image.wiaudbgerror">wiauDbgError</a> function except that the latter function has an additional parameter used to identify the function or method that is active when the function is called.


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
<a href="image.wiaudbgerror">wiauDbgError</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgLegacyError function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

