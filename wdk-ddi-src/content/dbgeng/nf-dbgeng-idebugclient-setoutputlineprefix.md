---
UID: NF:dbgeng.IDebugClient.SetOutputLinePrefix
title: IDebugClient::SetOutputLinePrefix method
author: windows-driver-content
description: Sets a prefix for multiple lines of output.
old-location: debugger\idebugclient_setoutputlineprefix.htm
old-project: debugger
ms.assetid: 59A3FD7D-153D-4580-84C1-2408A485F684
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient, IDebugClient::SetOutputLinePrefix, SetOutputLinePrefix
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient.SetOutputLinePrefix
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

# IDebugClient::SetOutputLinePrefix method



## -description
    Sets a prefix for multiple lines of output. 



## -syntax

````
HRESULT SetOutputLinePrefix(
  [in, optional] PCSTR Prefix
);
````


## -parameters

### -param Prefix [in, optional]

A pointer to the prefix value.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Some of the engine commands produce
    multiple lines of output.  This function sets a prefix that the engine adds to each line. This function allows the caller to control indentation or identifying marks.
    

 The prefix value  is not a general setting for any output
    that contains a newline. Methods which use
    the line prefix are marked in their documentation.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetOutputLinePrefix method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

