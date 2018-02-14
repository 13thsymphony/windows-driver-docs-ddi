---
UID: NF:dbgeng.IDebugRegisters2.SetValues2
title: IDebugRegisters2::SetValues2 method
author: windows-driver-content
description: The SetValues2 method sets the value of several of the target's registers.
old-location: debugger\setvalues2.htm
old-project: debugger
ms.assetid: 9505a0ce-4f4e-43af-97a2-653b5776c423
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugRegisters2::SetValues2, debugger.setvalues2, SetValues2 method [Windows Debugging], IDebugRegisters2, SetValues2, SetValues2 method [Windows Debugging], IDebugRegisters2 interface, IDebugRegisters_4e5c8f37-a5ad-4083-adb9-e75ec18542b2.xml, IDebugRegisters2 interface [Windows Debugging], SetValues2 method, IDebugRegisters2::SetValues2
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugRegisters2.SetValues2
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetValues2 method
The <b>SetValues2</b> method sets the value of several of the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.

## Syntax

````
HRESULT SetValues2(
  [in]           ULONG        Source,
  [in]           ULONG        Count,
  [in, optional] PULONG       Indices,
  [in]           ULONG        Start,
  [in]           PDEBUG_VALUE Values
);
````

## Parameters

`Source`

Specifies the register source to query.

The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context.

<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>
</td>
</tr>
</table>

`Count`

Specifies the number of registers for which to set the values.

`Indices`

Specifies an array that contains the indices of the registers for which to set the values.  The number of elements in this array is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used instead.

`Start`

If <i>Indices</i> is <b>NULL</b>, the registers will be set consecutively starting at this index.  Otherwise, it is ignored.

`Values`

An array that contains the values to which to set the registers.  The number of elements that this array holds is <i>Count</i>.  See <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a> for a description of this parameter type.


## Return Value

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>

## Remarks

The engine does its best to cast the values in <i>Values</i> into the type of the registers; this conversion is the same as that performed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539158">CoerceValue</a>.  If the value is larger than what the register can hold, the least significant bits are dropped.  Floating-point and integer conversions will also be performed if necessary.  

If the return value is not S_OK, some of the registers still might have been set.  

When a subregister is altered, the register that contains it is also altered.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include DbgEng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff597642">SetValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a>



<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::SetValues2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>