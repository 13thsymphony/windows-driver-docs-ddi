---
UID : NF:fwpsk.FwpsOpenToken0
title : FwpsOpenToken0 function
author : windows-driver-content
description : The FwpsOpenToken0 function opens an access token.
old-location : netvista\fwpsopentoken0.htm
old-project : netvista
ms.assetid : B6C61023-F840-4517-83C1-BC9CBDFC27B0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FwpsOpenToken0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with  Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FwpsOpenToken0
req.alt-loc : fwpsk.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= PASSIVE_LEVEL
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---


# FwpsOpenToken0 function
The <b>FwpsOpenToken0</b> function opens an access token.<div class="alert"><b>Note</b>  <b>FwpsOpenToken0</b> is a specific version of <b>FwpsOpenToken</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>

## Syntax

````
NTSTATUS NTAPI NTAPI FwpsOpenToken0(
  _In_  HANDLE engineHandle,
  _In_  LUID   modifiedId,
  _In_  DWORD  desiredAccess,
  _Out_ HANDLE *accessToken
);
````

## Parameters

`engineHandle`

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a> function to open a
     session to the filter engine.

`modifiedId`

Specifies an <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a> that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used.

`desiredAccess`

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list (<b>DACL</b>) to determine which accesses are granted or denied.

`accessToken`

Pointer to a caller-allocated variable that receives a handle to the newly opened access token.


## Return Value

The 
     <b>FwpsOpenToken0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The access token was successfully opened.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | <= PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsOpenToken0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>