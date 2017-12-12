---
UID: NC.ndis.MINIPORT_CO_DEACTIVATE_VC
title: MINIPORT_CO_DEACTIVATE_VC
author: windows-driver-content
description: The MiniportCoDeactivateVc function is required for connection-oriented miniports.
old-location: netvista\miniportcodeactivatevc.htm
old-project: netvista
ms.assetid: 8c17cec8-d161-47cf-b886-bb8b8d957656
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoDeactivateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoDeactivateVc (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportCoDeactivateVc
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# MINIPORT_CO_DEACTIVATE_VC callback



## -description
The 
  <i>MiniportCoDeactivateVc</i> function is required for connection-oriented miniports. 
  <i>MiniportCoDeactivateVc</i> is called by NDIS to indicate that a VC is being marked as unusable.



## -prototype

````
MINIPORT_CO_DEACTIVATE_VC MiniportCoDeactivateVc;

NDIS_STATUS MiniportCoDeactivateVc(
  _In_ NDIS_HANDLE MiniportVcContext
)
{ ... }
````


## -parameters

### -param MiniportVcContext [in]

Specified the handle to a miniport driver-allocated context area in which the miniport driver
     maintains state information per-VC. The miniport driver supplied this handle to NDIS from its 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> function.


## -returns
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>Indicates that the miniport driver successfully halted any communication across the VC and
       marked it as unusable.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>Indicates that the miniport driver will complete the request to halt the VC asynchronously. When
       the miniport driver has completed halting the VC, it must then call 
       <a href="netvista.ndismcodeactivatevccomplete">
       NdisMCoDeactivateVcComplete</a> to signal NDIS that this operation has been completed.

 


## -remarks
<i>MiniportCoDeactivateVc</i> communicates with its network adapter to terminate all communication across
    this VC (in other words, deprogramming receive or send buffers on the adapter). The miniport driver
    should also mark the VC, it its context area, as being inactive to prevent any further communication
    across the VC.

There is not a one-to-one relationship between calls to 
    <a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a> and 
    <i>MiniportCoDeactivateVc</i>. While NDIS may call 
    <i>MiniportCoActivateVc</i> multiple times on a single VC, only one call to 
    <i>MiniportCoDeactivateVc</i> is made to shut down a virtual connection. For example, a VC can be reused
    for different calls possibly causing multiple calls to 
    <i>MiniportCoActivateVc</i>.

To define a <i>MiniportCoDeactivateVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoDeactivateVc</i> function that is named "MyCoDeactivateVc", use the <b>MINIPORT_CO_DEACTIVATE_VC</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_CO_DEACTIVATE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_DEACTIVATE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/92f5547c-3992-4090-93fb-ffcd872f9641">MiniportCoDeactivateVc (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>MiniportCoDeactivateVc (NDIS
   5.1)</i>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>
</dt>
<dt>
<a href="netvista.ndismcodeactivatevccomplete">NdisMCoDeactivateVcComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CO_DEACTIVATE_VC callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

