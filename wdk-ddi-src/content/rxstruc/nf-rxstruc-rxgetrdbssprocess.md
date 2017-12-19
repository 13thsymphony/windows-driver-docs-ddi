---
UID: NF.rxstruc.RxGetRDBSSProcess
title: RxGetRDBSSProcess function
author: windows-driver-content
description: RxGetRDBSSProcess returns a pointer to the process of the main thread used by the RDBSS kernel process.
old-location: ifsk\rxgetrdbssprocess.htm
old-project: ifsk
ms.assetid: 2d3717c2-c809-48b9-a84b-1e69a04b767e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxGetRDBSSProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxstruc.h
req.include-header: Rxstruc.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxGetRDBSSProcess
req.alt-loc: rxstruc.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# RxGetRDBSSProcess function



## -description
<b>RxGetRDBSSProcess</b> returns a pointer to the process of the main thread used by the RDBSS kernel process.



## -syntax

````
PEPROCESS RxGetRDBSSProcess(void);
````


## -parameters


## -returns
<b>RxGetRDBSSProcess</b> returns a pointer to the kernel process of the main thread used by RDBSS.

<b>RxGetRDBSSProcess</b> returns a pointer to the kernel process of the main thread used by RDBSS.

<b>RxGetRDBSSProcess</b> returns a pointer to the kernel process of the main thread used by RDBSS.


## -remarks
When <b>RxDriverEntry</b> is called to initialize RDBSS, a pointer to the kernel process that is running is retreived by calling <b>PsGetCurrentProcess</b> and stored in an internal RDBSS data structure. This value is returned when <b>RxGetRDBSSProcess</b> is called. This value is sometimes called the file system process. 


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
<dt>Rxstruc.h (include Rxstruc.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>
</dt>
<dt>
<a href="ifsk.rxdriverentry">RxDriverEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxGetRDBSSProcess function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

