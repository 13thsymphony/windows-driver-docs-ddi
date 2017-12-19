---
UID: NF.dbgeng.IDebugControl3.CoerceValue
title: IDebugControl3::CoerceValue method
author: windows-driver-content
description: The CoerceValue method converts a value of one type into a value of another type.
old-location: debugger\coercevalue.htm
old-project: Debugger
ms.assetid: db037fc8-d503-4a72-b6bc-d5189f6786d4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugControl3, IDebugControl3::CoerceValue, CoerceValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl.CoerceValue,IDebugControl2.CoerceValue,IDebugControl3.CoerceValue
req.alt-loc: Dbgeng.h
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

# IDebugControl3::CoerceValue method



## -description
The <b>CoerceValue</b> method converts a value of one type into a value of another type.



## -syntax

````
HRESULT CoerceValue(
  [in]  PDEBUG_VALUE In,
  [in]  ULONG        OutType,
  [out] PDEBUG_VALUE Out
);
````


## -parameters

### -param In [in]

Specifies the value to be converted


### -param OutType [in]

Specifies the desired type for the converted value. See <a href="debugger.debug_value">DEBUG_VALUE</a> for possible values.


### -param Out [out]

Receives the converted value.  The type of this value will be the type specified by <i>OutType</i>.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method converts a value of one type into a value of another type.  If the specified <i>OutType</i> is not capable of containing the information supplied by the <i>In</i> variable, data will be lost.


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="debugger.debug_value">DEBUG_VALUE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::CoerceValue method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

