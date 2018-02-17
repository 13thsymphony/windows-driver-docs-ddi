---
UID: NC:ndis.MINIPORT_CO_CREATE_VC
title: MINIPORT_CO_CREATE_VC
author: windows-driver-content
description: The MiniportCoCreateVc function is required for connection-oriented miniports.
old-location: netvista\miniportcocreatevc.htm
old-project: netvista
ms.assetid: 99eaba29-ce17-4e79-878e-5fdf7411e56c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportcocreatevc, MiniportCoCreateVc callback function [Network Drivers Starting with Windows Vista], MiniportCoCreateVc, MINIPORT_CO_CREATE_VC, MINIPORT_CO_CREATE_VC, ndis/MiniportCoCreateVc, condis_miniport_ref_73192f8d-af71-40f8-8118-52124bc38e94.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoCreateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoCreateVc (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	MiniportCoCreateVc
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---


# MINIPORT_CO_CREATE_VC function
The 
  <i>MiniportCoCreateVc</i> function is required for connection-oriented miniports. 
  <i>MiniportCoCreateVc</i> is called by NDIS to indicate to the miniport driver that a
  new VC is being created.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CO_CREATE_VC</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_CO_CREATE_VC MiniportCoCreateVc;

NDIS_STATUS MiniportCoCreateVc(
  NDIS_HANDLE MiniportAdapterContext,
  NDIS_HANDLE NdisVcHandle,
  PNDIS_HANDLE MiniportVcContext
)
{...}
```

## Parameters

`MiniportAdapterContext`

Specifies the handle to a miniport driver-allocated context area in which the miniport driver
     maintains state information about this instance of the adapter. The miniport driver provided this handle
     to NDIS by calling 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

`NdisVcHandle`

Specifies a handle, supplied by NDIS, that uniquely identifies the VC being created. This handle
     is opaque to the miniport driver and reserved for NDIS library use.

`MiniportVcContext`

Specifies, on output, a handle to a miniport driver-supplied context area in which the miniport
     driver maintains state about the VC.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the miniport driver successfully allocated all necessary resources and prepared
       itself for handling requests for the newly created VC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager could not obtain dynamically allocated resources necessary for
       it to operate on the new VC.

</td>
</tr>
</table>

## Remarks

<i>MiniportCoCreateVc</i> must be written as a synchronous function and cannot, under
    any circumstances, return NDIS_STATUS_PENDING without causing a system-wide failure.

<i>MiniportCoCreateVc</i> allocates any necessary resources that the miniport driver
    requires to maintain state information about the VC. The resources could include, but are not limited to
    memory buffers, events, data structures, and other such similar resources.

After allocating all required resources the miniport driver should initialize the resources into a
    usable state and return a pointer to the state area in 
    <i>MiniportVcContext</i>. The handle is set by dereferencing the handle and storing a
    pointer to the state buffer as the value of the handle. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>*MiniportVcContext = SomeBuffer;</pre>
</td>
</tr>
</table></span></div>
Miniport drivers 
    <i>must</i> store the handle to the VC, 
    <i>NdisVcHandle</i>, in their state area as it is a required parameter to other NDIS
    library routines that are subsequently called by the miniport driver.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCoCreateVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoCreateVc</i> function that is named "MyCoCreateVc", use the <b>MINIPORT_CO_CREATE_VC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CO_CREATE_VC MyCoCreateVc;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MyCoCreateVc(
    NDIS_HANDLE  MiniportAdapterContext,
    NDIS_HANDLE  NdisVcHandle,
    PNDIS_HANDLE  MiniportVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CO_CREATE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_CREATE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoCreateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoCreateVc (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Windows |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CO_CREATE_VC callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>