---
UID: NF:dbgeng.IDebugControl4.GetExtensionByPathWide
title: IDebugControl4::GetExtensionByPathWide method
author: windows-driver-content
description: The GetExtensionByPathWide method returns the handle for an already loaded extension library.
old-location: debugger\getextensionbypathwide.htm
old-project: debugger
ms.assetid: 85257190-2b39-487d-ada6-4c8cd0b1450f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::GetExtensionByPathWide, GetExtensionByPathWide
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
req.alt-api: IDebugControl4.GetExtensionByPathWide
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

# IDebugControl4::GetExtensionByPathWide method



## -description
The <b>GetExtensionByPathWide</b>  method returns the handle for an already loaded extension library.



## -syntax

````
HRESULT GetExtensionByPathWide(
  [in]  PCWSTR   Path,
  [out] PULONG64 Handle
);
````


## -parameters

### -param Path [in]

Specifies the fully qualified path and file name of the extension library.


### -param Handle [out]

Receives the handle of the extension library.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Extension libraries are loaded into the <a href="debugger.debugging_session_and_execution_model#host_engine#host_engine">host engine</a>, which is where this method looks for the requested extension library.  <i>Path</i> is a path and file name for the host engine.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetExtensionByPathWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

