---
UID: NF:rilapi.RIL_OpenUiccLogicalChannel
title: RIL_OpenUiccLogicalChannel function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_openuicclogicalchannel.htm
old-project: netvista
ms.assetid: 8e77d55d-62f5-450c-9d9a-41acfece84c0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_OpenUiccLogicalChannel, RIL_OpenUiccLogicalChannel, netvista.ril_openuicclogicalchannel, RIL_OpenUiccLogicalChannel method [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapi.h
apiname:
-	RIL_OpenUiccLogicalChannel
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_OpenUiccLogicalChannel function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_OpenUiccLogicalChannel(
   HRIL        hRil,
   LPVOID      lpContext,
   DWORD       dwSlotIndex,
   DWORD       dwChannelGroup,
   DWORD       dwAppIdLength,
   const BYTE  pbAppId,
   DWORD       dwSelectP2Arg
);
````

## Parameters

`hRil`



`lpContext`



`dwSlotIndex`



`dwChannelGroup`



`dwAppIdLength`



`pbAppId`



`dwSelectP2Arg`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |