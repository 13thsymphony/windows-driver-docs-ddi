---
UID: NF:dbgeng.IDebugClient5.GetOutputMask
title: IDebugClient5::GetOutputMask method
author: windows-driver-content
description: The GetOutputMask method returns the output mask currently set for the client.
old-location: debugger\getoutputmask.htm
old-project: debugger
ms.assetid: b1076b17-9175-4823-abb7-1c864670e8d5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::GetOutputMask, GetOutputMask
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
req.alt-api: IDebugClient.GetOutputMask,IDebugClient2.GetOutputMask,IDebugClient3.GetOutputMask,IDebugClient4.GetOutputMask,IDebugClient5.GetOutputMask
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetOutputMask method



## -description
The <b>GetOutputMask</b> method returns the output mask currently set for the client.



## -syntax

````
HRESULT GetOutputMask(
  [out] PULONG Mask
);
````


## -parameters

### -param Mask [out]

Receives the output mask for the client.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details on how to interpret this value.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For an overview of output in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetOutputMask method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

