---
UID: NC:ndis.FILTER_RETURN_NET_BUFFER_LISTS
title: FILTER_RETURN_NET_BUFFER_LISTS
author: windows-driver-content
description: NDIS calls the FilterReturnNetBufferLists function to return a linked list of NET_BUFFER_LIST structures and associated data to a filter driver.Note  You must declare the function by using the FILTER_RETURN_NET_BUFFER_LISTS type.
old-location: netvista\filterreturnnetbufferlists.htm
old-project: netvista
ms.assetid: 8d7e362f-62da-4ce7-9497-1cfaff2b678e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.filterreturnnetbufferlists, FilterReturnNetBufferLists callback function [Network Drivers Starting with Windows Vista], FilterReturnNetBufferLists, FILTER_RETURN_NET_BUFFER_LISTS, FILTER_RETURN_NET_BUFFER_LISTS, ndis/FilterReturnNetBufferLists, filter_functions_ref_a4a0c4ae-790b-43f9-a209-06538a7bbab6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	FilterReturnNetBufferLists
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---


# FILTER_RETURN_NET_BUFFER_LISTS function
NDIS calls the 
  <i>FilterReturnNetBufferLists</i> function to return a linked list of 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures and associated data
  to a filter driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_RETURN_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
FILTER_RETURN_NET_BUFFER_LISTS FilterReturnNetBufferLists;

void FilterReturnNetBufferLists(
  NDIS_HANDLE FilterModuleContext,
  PNET_BUFFER_LIST NetBufferLists,
  ULONG ReturnFlags
)
{...}
```

## Parameters

`FilterModuleContext`

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`NetBufferLists`

A linked list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that the filter driver indicated by calling the 
     <a href="..\ndis\nf-ndis-ndisfindicatereceivenetbufferlists.md">
     NdisFIndicateReceiveNetBufferLists</a> function. The list can include <b>NET_BUFFER_LIST</b> structures from
     multiple calls to 
     <b>NdisFIndicateReceiveNetBufferLists</b>.

`ReturnFlags`

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero.This function supports the following flags: 





#### NDIS_RETURN_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_RECEIVE_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>ReceiveFlags</i> parameter of <a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>  when it sends the request.</div>
<div> </div>


## Return Value

None

## Remarks

<i>FilterReturnNetBufferLists</i> is an optional function. If a filter driver does not filter receive indications, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function.

The filter driver can call the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function,
    from the 
    <a href="..\ndis\nc-ndis-filter_set_module_options.md">FilterSetModuleOptions</a> function, to
    specify a 
    <i>FilterReturnNetBufferLists</i> function for a filter module.

<div class="alert"><b>Note</b>  A filter driver that does not provide a 
    <i>FilterReturnNetBufferLists</i> function cannot call the 
    <a href="..\ndis\nf-ndis-ndisfindicatereceivenetbufferlists.md">
    NdisFIndicateReceiveNetBufferLists</a> function to initiate a receive indication.</div>
<div> </div>
<div class="alert"><b>Note</b>  A filter driver that does provide a 
    <i>FilterReturnNetBufferLists</i> function must provide a 
    <a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a> function.</div>
<div> </div>
When NDIS calls 
    <i>FilterReturnNetBufferLists</i>, the filter driver regains ownership of the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures and associated
    data.

If an underlying driver initiated the receive indication, the filter driver should call the 
    <a href="..\ndis\nf-ndis-ndisfreturnnetbufferlists.md">
    NdisFReturnNetBufferLists</a> function to complete the receive indication.

If the filter driver originated the receive indication, 
    <i>FilterReturnNetBufferLists</i> can either release the NET_BUFFER_LIST structures and associated data or
    prepare them for reuse in a subsequent call to 
    <b>NdisFIndicateReceiveNetBufferLists</b>.

A filter driver should keep track of receive indications that it initiates and make sure that it does
    not call 
    <b>NdisFReturnNetBufferLists</b> when NDIS calls 
    <i>FilterReturnNetBufferLists</i>.

NDIS calls 
    <i>FilterReturnNetBufferLists</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterReturnNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterReturnNetBufferLists</i> function that is named "MyReturnNetBufferLists", use the <b>FILTER_RETURN_NET_BUFFER_LISTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_RETURN_NET_BUFFER_LISTS MyReturnNetBufferLists;</pre>
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
VOID
 MyReturnNetBufferLists(
    NDIS_HANDLE  FilterModuleContext,
    PNET_BUFFER_LIST  NetBufferLists,
    ULONG  ReturnFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_RETURN_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_RETURN_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Target Platform** | Windows |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-filter_set_module_options.md">FilterSetModuleOptions</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nf-ndis-ndisfindicatereceivenetbufferlists.md">
   NdisFIndicateReceiveNetBufferLists</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a>



<a href="..\ndis\nf-ndis-ndisfreturnnetbufferlists.md">NdisFReturnNetBufferLists</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_RETURN_NET_BUFFER_LISTS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>