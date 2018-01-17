---
UID: NF:dbgeng.IDebugPlmClient.LaunchPlmPackageForDebugWide
title: IDebugPlmClient::LaunchPlmPackageForDebugWide method
author: windows-driver-content
description: Launches a suspended Process Lifecycle Management (PLM) application.
old-location: debugger\idebugplmclient_launchplmpackagefordebugwide.htm
old-project: debugger
ms.assetid: DE11B4A5-5AE3-4369-AF6D-6CE34B9AAFAB
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugPlmClient, IDebugPlmClient::LaunchPlmPackageForDebugWide, LaunchPlmPackageForDebugWide
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
req.alt-api: IDebugPlmClient.LaunchPlmPackageForDebugWide
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

# IDebugPlmClient::LaunchPlmPackageForDebugWide method



## -description
Launches a suspended Process Lifecycle Management (PLM) application.



## -syntax

````
HRESULT LaunchPlmPackageForDebugWide(
  [in]           ULONG64 Server,
  [in]           ULONG   Timeout,
  [in]           PCWSTR  PackageFullName,
  [in]           PCWSTR  AppName,
  [in, optional] PCWSTR  Arguments,
  [out]          PULONG  ProcessId,
  [out]          PULONG  ThreadId
);
````


## -parameters

### -param Server [in]

The server of the application.


### -param Timeout [in]

A time-out value.


### -param PackageFullName [in]

A pointer to the package name.


### -param AppName [in]

A pointer to the application name. 


### -param Arguments [in, optional]

A pointer an arguments string.


### -param ProcessId [out]

A pointer to a process ID output.


### -param ThreadId [out]

A pointer to a thread ID output.


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugplmclient.md">IDebugPlmClient</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugPlmClient::LaunchPlmPackageForDebugWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

