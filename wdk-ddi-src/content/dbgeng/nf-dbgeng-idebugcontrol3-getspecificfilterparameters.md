---
UID: NF:dbgeng.IDebugControl3.GetSpecificFilterParameters
title: IDebugControl3::GetSpecificFilterParameters method
author: windows-driver-content
description: The GetSpecificFilterParameters method returns the parameters for specific event filters.
old-location: debugger\getspecificfilterparameters.htm
old-project: debugger
ms.assetid: d2140270-558d-4cd9-b497-f61be40c7a87
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetSpecificFilterParameters, GetSpecificFilterParameters
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
req.alt-api: IDebugControl.GetSpecificFilterParameters,IDebugControl2.GetSpecificFilterParameters,IDebugControl3.GetSpecificFilterParameters
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::GetSpecificFilterParameters method



## -description
The <b>GetSpecificFilterParameters</b> method returns the parameters for specific event filters.



## -syntax

````
HRESULT GetSpecificFilterParameters(
  [in]  ULONG                             Start,
  [in]  ULONG                             Count,
  [out] PDEBUG_SPECIFIC_FILTER_PARAMETERS Params
);
````


## -parameters

### -param Start [in]

Specifies the index of the first specific event filter whose parameters will be returned.


### -param Count [in]

Specifies the number of specific event filters to return parameters for.


### -param Params [out]

Receives the parameters for the specific event filters.  <i>Params</i> is an array of elements of type <a href="..\dbgeng\ns-dbgeng-_debug_specific_filter_parameters.md">DEBUG_SPECIFIC_FILTER_PARAMETERS</a>.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about <a href="debugger.events#event_filters#event_filters">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.


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
<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556795">SetSpecificFilterParameters</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546650">GetExceptionFilterParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetSpecificFilterParameters method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

