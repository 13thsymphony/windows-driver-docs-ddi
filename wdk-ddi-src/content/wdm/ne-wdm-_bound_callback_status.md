---
UID: NE.wdm._BOUND_CALLBACK_STATUS
title: _BOUND_CALLBACK_STATUS
author: windows-driver-content
description: The BOUND_CALLBACK_STATUS enumeration indicates how a user-mode bounds exception was processed by the BoundCallback function.
old-location: kernel\bound_callback_status.htm
old-project: kernel
ms.assetid: 874FB2E1-7A2F-4C91-BA72-D67DA2EE84E1
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _BOUND_CALLBACK_STATUS, *PBOUND_CALLBACK_STATUS, BOUND_CALLBACK_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BOUND_CALLBACK_STATUS
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# _BOUND_CALLBACK_STATUS enumeration



## -description
The <b>BOUND_CALLBACK_STATUS</b> enumeration indicates how a user-mode bounds exception was processed by the <a href="kernel.boundcallback">BoundCallback</a> function.



## -syntax

````
typedef enum _BOUND_CALLBACK_STATUS { 
  BoundExceptionContinueSearch  = 0,
  BoundExceptionHandled,
  BoundExceptionError,
  BoundExceptionMaximum
} BOUND_CALLBACK_STATUS;
````


## -enum-fields

### -field BoundExceptionContinueSearch

The bounds exception was not handled by the callback, and the exception should continue to propagate.  


### -field BoundExceptionHandled

The exception was handled by the callback, and the exception should not propagate any further. 


### -field BoundExceptionError

The user mode process should be terminated by the system.


### -field BoundExceptionMaximum

This value is not currently used.


## -remarks
The return value of the <a href="kernel.boundcallback">BoundCallback</a> routine is a <b>BOUND_CALLBACK_STATUS</b> value.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.boundcallback">BoundCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BOUND_CALLBACK_STATUS enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

