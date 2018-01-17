---
UID: NF:fwpmk.FwpmCalloutAdd0
title: FwpmCalloutAdd0 function
author: windows-driver-content
description: The FwpmCalloutAdd0 function adds a callout to the filter engine.Note  FwpmCalloutAdd0 is a specific version of FwpmCalloutAdd.
old-location: netvista\fwpmcalloutadd0.htm
old-project: netvista
ms.assetid: f88a31c4-f42c-487d-b6d8-f8f609f2faff
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpmCalloutAdd0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpmCalloutAdd0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: FLT_VOLUME_PROPERTIES, *PFLT_VOLUME_PROPERTIES
---

# FwpmCalloutAdd0 function



## -description
The 
  <b>FwpmCalloutAdd0</b> function adds a callout to the filter engine.



## -syntax

````
NTSTATUS NTAPI FwpmCalloutAdd0(
  _In_            HANDLE               engineHandle,
  _In_      const FWPM_CALLOUT0        *callout,
  _In_opt_        PSECURITY_DESCRIPTOR sd,
  _Out_opt_       UINT32               *id
);
````


## -parameters

### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a> function to open a
     session to the filter engine.


### -param callout [in]

A pointer to a constant 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550076">FWPM_CALLOUT0</a> structure that contains the
     data that is required to add the callout to the filter engine.


### -param sd [in, optional]

A pointer to a constant <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure that describes the security descriptor for
     the callout that is being added to the filter engine. This parameter is optional and can be <b>NULL</b>.


### -param id [out, optional]

A pointer to a UINT32-typed variable that receives a run-time identifier that identifies the
     callout in the filter engine. This is the same identifier that is returned when a callout driver
     registers the callout driver's callout functions with the filter engine. The callout driver passes this
     identifier to the 
     <a href="..\fwpmk\nf-fwpmk-fwpmcalloutdeletebyid0.md">FwpmCalloutDeleteById0</a> function
     when removing the callout from the filter engine. This parameter is optional and can be <b>NULL</b>.


## -returns
The 
     <b>FwpmCalloutAdd0</b> function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callout was successfully added to the filter engine.
<dl>
<dt><b>STATUS_FWP_ALREADY_EXISTS</b></dt>
</dl>The callout could not be added to the filter engine. A callout already exists in the filter
       engine with an identifier identical to the GUID specified in the 
       <b>calloutKey</b> member of the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff550076">FWPM_CALLOUT0</a> structure pointed to by the 
       <i>callout</i> parameter.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A callout driver calls the 
    <b>FwpmCalloutAdd0</b> function to add a callout to the filter engine.

Callout drivers do not typically add their callouts to the filter engine. In most situations this is
    handled by a user-mode Windows Filtering Platform management application.

A callout and filters that specify the callout for the filter's action can be added to the filter
    engine before a callout driver registers the callout with the filter engine. In this situation, filters
    with an action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated as
    <b>FWP_ACTION_BLOCK</b> and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored until the
    callout is registered with the filter engine.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550076">FWPM_CALLOUT0</a>
</dt>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmcalloutdeletebyid0.md">FwpmCalloutDeleteById0</a>
</dt>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmcalloutdeletebykey0.md">FwpmCalloutDeleteByKey0</a>
</dt>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/d9539403-7657-4e95-8791-309673d1207d">Types of Callouts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmCalloutAdd0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

