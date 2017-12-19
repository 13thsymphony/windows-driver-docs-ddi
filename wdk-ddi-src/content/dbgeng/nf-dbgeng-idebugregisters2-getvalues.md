---
UID: NF.dbgeng.IDebugRegisters2.GetValues
title: IDebugRegisters2::GetValues method
author: windows-driver-content
description: The GetValues method gets the value of several of the target's registers.
old-location: debugger\getvalues.htm
old-project: Debugger
ms.assetid: d78c54a7-04a5-4c51-bf33-a5b7fb937897
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugRegisters2, IDebugRegisters2::GetValues, GetValues
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugRegisters.GetValues,IDebugRegisters2.GetValues
req.alt-loc: dbgeng.h
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

# IDebugRegisters2::GetValues method



## -description
The <b>GetValues</b> method gets the value of several of the target's <a href="debugger.x86_architecture#registers#registers">registers</a>.



## -syntax

````
HRESULT GetValues(
  [in]           ULONG        Count,
  [in, optional] PULONG       Indices,
  [in]           ULONG        Start,
  [out]          PDEBUG_VALUE Values
);
````


## -parameters

### -param Count [in]

Specifies the number of registers whose values are requested.


### -param Indices [in, optional]

Specifies an array that contains the indices of the registers from which to get the values.  The number of elements in this array is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

If <i>Indices</i> is <b>NULL</b>, the registers will be read consecutively starting at this index.  Otherwise it is ignored.


### -param Values [out]

Receives the values of the registers.  The number of elements this array holds is <i>Count</i>.  See <a href="debugger.debug_value">DEBUG_VALUE</a> for a description of this parameter type.


## -returns
This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>The target is not accessible, or one of the registers could not be accessed.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The value of the index of one of the registers is greater than the number of registers on the target machine.  Partial results might have been obtained; those registers that could not be read will have the type DEBUG_VALUE_INVALID.

 


## -remarks
<b>GetValues</b> gets the value of several of the target's registers.

If the return value is not S_OK, some of the registers still might have been read.  If the target was not accessible, the return type is E_UNEXPECTED and <i>Values</i> is unchanged; otherwise, <i>Values</i> will contain partial results and the registers that could not be read will have type DEBUG_VALUE_INVALID.  Ambiguity in the case of the return value E_UNEXPECTED can be avoided by setting the memory of <i>Values</i> to zero before calling this method.

To receive the value of only a single register, use the <a href="debugger.getvalue">GetValue</a> method instead.

The method <a href="debugger.getvalues2">GetValues2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.


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
<dt>Dbgeng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>
</dt>
<dt>
<a href="debugger.getvalue">GetValue</a>
</dt>
<dt>
<a href="debugger.getvalues2">GetValues2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugRegisters::GetValues method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

