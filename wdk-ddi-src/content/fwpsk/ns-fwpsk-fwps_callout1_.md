---
UID : NS:fwpsk.FWPS_CALLOUT1_
title : FWPS_CALLOUT1_
author : windows-driver-content
description : The FWPS_CALLOUT1 structure defines the data that is required for a callout driver to register a callout with the filter engine.Note  FWPS_CALLOUT1 is the specific version of FWPS_CALLOUT used in Windows 7 and later.
old-location : netvista\fwps_callout1.htm
old-project : netvista
ms.assetid : d15c4cd4-b4f0-4363-988a-2bbb235b7b37
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FWPS_CALLOUT1_, FWPS_CALLOUT1
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FWPS_CALLOUT1
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
req.irql : <= DISPATCH_LEVEL
req.typenames : FWPS_CALLOUT1
---

# FWPS_CALLOUT1_ structure
The <b>FWPS_CALLOUT1</b> structure defines the data that is required for a callout driver to register a
  callout with the filter engine.

## Syntax
````
typedef struct FWPS_CALLOUT1_ {
  GUID                                calloutKey;
  UINT32                              flags;
  FWPS_CALLOUT_CLASSIFY_FN1           classifyFn;
  FWPS_CALLOUT_NOTIFY_FN1             notifyFn;
  FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0 flowDeleteFn;
} FWPS_CALLOUT1;
````

## Members

        
            `calloutKey`

            A callout driver-defined <b>GUID</b> that uniquely identifies the callout.
        
            `classifyFn`

            A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a> callout function. The filter
     engine calls this function whenever there is network data to be processed by the callout.
        
            `flags`

            Flags that specify callout-specific parameters. Possible flags are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
        
            `flowDeleteFn`

            A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function. The filter
     engine calls this function whenever a data flow that is being processed by the callout is terminated.
     

If a callout driver does not associate a context with the data flows that the callout processes, then
     this member should be set to <b>NULL</b>.
        
            `notifyFn`

            A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a> function. The filter engine calls
     this function to notify the callout driver about events that are associated with the callout.

    ## Remarks
        A callout driver passes a pointer to an initialized <b>FWPS_CALLOUT1</b> structure to the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a> function when it
    registers a callout with the filter engine.

A callout can set the <b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b> flag only for connections on which
    the driver is interested in performing stream inspections. This callout will be ignored on all other
    connections. Performance will be improved and the driver will not have to maintain unnecessary state
    data.

This structure is essentially identical to the previous version, 
    <a href="..\fwpsk\ns-fwpsk-fwps_callout0_.md">FWPS_CALLOUT0</a>. The only differences are that
    the members of this version store the updated versions of the callout function pointers, and additional flags are available for callout drivers to set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |

    ## See Also

        <dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn1.md">notifyFn1</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_callout0_.md">FWPS_CALLOUT0</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_callout2_.md">FWPS_CALLOUT2</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT1 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>