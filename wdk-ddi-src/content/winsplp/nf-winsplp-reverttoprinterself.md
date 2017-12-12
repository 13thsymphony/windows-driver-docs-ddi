---
UID: NF.winsplp.RevertToPrinterSelf
title: RevertToPrinterSelf function
author: windows-driver-content
description: When RevertToPrinterSelf is called on an impersonating thread, it returns the token for the thread that is being impersonated.
old-location: print\reverttoprinterself.htm
old-project: print
ms.assetid: 3d94d363-fc8b-4b12-b90d-43dfc5923bdf
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: RevertToPrinterSelf
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RevertToPrinterSelf
req.alt-loc: Spoolss.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
req.product: Windows 10 or later.
---

# RevertToPrinterSelf function



## -description
When <code>RevertToPrinterSelf</code> is called on an impersonating thread, it returns the token for the thread that is being impersonated.



## -syntax

````
HANDLE RevertToPrinterSelf(
    void
);
````


## -parameters

### -param void 


## -returns
If the operation succeeds, the function returns the token of the impersonated thread. If the current thread is not impersonating another thread, this function returns <b>NULL</b>.


## -remarks
<code>RevertToPrinterSelf</code> should be called when a component needs access to resources from the local system context, such as the registry. The local system context is the security context (the collection of settings that define the security behavior of a process or thread) of the system process. The system process is the process that runs in the logon session that is created for the local system account when the operating system boots. 

If <code>RevertToPrinterSelf</code> returns a non-<b>NULL</b> value, <a href="print.impersonateprinterclient">ImpersonatePrinterClient</a> must be called with the return value to complete the operation and clean up the thread handle.


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
Header

</th>
<td width="70%">
<dl>
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Spoolss.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Spoolss.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.impersonateprinterclient">ImpersonatePrinterClient</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RevertToPrinterSelf function%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

