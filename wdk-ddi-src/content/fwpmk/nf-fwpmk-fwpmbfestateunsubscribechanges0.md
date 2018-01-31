---
UID : NF:fwpmk.FwpmBfeStateUnsubscribeChanges0
title : FwpmBfeStateUnsubscribeChanges0 function
author : windows-driver-content
description : The FwpmBfeStateUnsubscribeChanges0 function deregisters a base filtering engine (BFE) callback function that was previously registered by calling the FwpmBfeStateSubscribeChanges0 function.Note  FwpmBfeStateUnsubscribeChanges0 is a specific version of FwpmBfeStateUnsubscribeChanges. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location : netvista\fwpmbfestateunsubscribechanges0.htm
old-project : netvista
ms.assetid : 1a84401a-d7da-43d2-925d-0d6ed370c980
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wfp_ref_2_funct_2_fwpm_2b1f650b-81ab-4dd9-be56-97039f86ac1e.xml, netvista.fwpmbfestateunsubscribechanges0, fwpmk/FwpmBfeStateUnsubscribeChanges0, FwpmBfeStateUnsubscribeChanges0 function [Network Drivers Starting with Windows Vista], FwpmBfeStateUnsubscribeChanges0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpmk.h
req.include-header : Fwpmk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fwpkclnt.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---


# FwpmBfeStateUnsubscribeChanges0 function
The 
  <b>FwpmBfeStateUnsubscribeChanges0</b> function deregisters a base filtering engine (BFE) callback function that was previously
  registered by calling the 
  <mshelp:link keywords="netvista.fwpmbfestatesubscribechanges0" tabindex="0"><b>
  FwpmBfeStateSubscribeChanges0</b></mshelp:link> function.
<div class="alert"><b>Note</b>  <b>FwpmBfeStateUnsubscribeChanges0</b> is a specific version of <b>FwpmBfeStateUnsubscribeChanges</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpmBfeStateUnsubscribeChanges0(
  _Inout_ HANDLE changeHandle
);
````

## Parameters

`changeHandle`

A handle associated with the registration of the callback function that is being deregistered.
     This handle was returned to the callout driver when it called the 
     <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">FwpmBfeStateSubscribeChanges0</a> function to register the callback function.


## Return Value

The 
     <b>FwpmBfeStateUnsubscribeChanges0</b> function returns one of the following NTSTATUS codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callback function was successfully deregistered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## Remarks

A callout driver calls the 
    <b>FwpmBfeStateUnsubscribeChanges0</b> function to deregister a callback function that was previously
    registered by calling the 
    <mshelp:link keywords="netvista.fwpmbfestatesubscribechanges0" tabindex="0"><b>
    FwpmBfeStateSubscribeChanges0</b></mshelp:link> function.

If a callout driver registers a callback function by calling the 
    <mshelp:link keywords="netvista.fwpmbfestatesubscribechanges0" tabindex="0"><b>
    FwpmBfeStateSubscribeChanges0</b></mshelp:link> function, it must deregister the callback function before the callout
    driver can be unloaded.

Do not call <b>FwpmBfeStateUnsubscribeChanges0</b> from a callback function that your driver previously registered by calling <mshelp:link keywords="netvista.fwpmbfestatesubscribechanges0" tabindex="0"><b>
    FwpmBfeStateSubscribeChanges0</b></mshelp:link>. Doing so can cause a deadlock.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpmk.h (include Fwpmk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="netvista.fwpmbfestatesubscribechanges0" tabindex="0"><b>
   FwpmBfeStateSubscribeChanges0</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmBfeStateUnsubscribeChanges0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>