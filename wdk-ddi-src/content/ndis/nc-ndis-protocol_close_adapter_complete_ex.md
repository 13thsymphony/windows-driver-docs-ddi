---
UID : NC:ndis.PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
title : PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
author : windows-driver-content
description : NDIS calls a protocol driver's ProtocolCloseAdapterCompleteEx function to complete a close adapter operation for which the NdisCloseAdapterEx function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX type. For more information, see the following Examples section.
old-location : netvista\protocolcloseadaptercompleteex.htm
old-project : netvista
ms.assetid : 62cc047a-bc91-4e1e-817e-7fd509d4d90e
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RxNameCacheInitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ProtocolCloseAdapterCompleteEx
req.alt-loc : Ndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX function
NDIS calls a protocol driver's 
  <i>ProtocolCloseAdapterCompleteEx</i> function to complete a close adapter operation for which the 
  <a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a> function returned
  NDIS_STATUS_PENDING.

## Syntax

```
PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX ProtocolCloseAdapterCompleteEx;

void ProtocolCloseAdapterCompleteEx(
  NDIS_HANDLE ProtocolBindingContext
)
{...}
```

## Parameters

`ProtocolBindingContext`

A handle to a context area allocated by the protocol driver. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.


## Return Value

None

## Remarks

<i>ProtocolCloseAdapterCompleteEx</i> is a required function.

If 
    <i>ProtocolUnbindAdapterEx</i> is waiting for NDIS to call 
    <i>ProtocolCloseAdapterCompleteEx</i>, this function can simply indicate that it has been called and
    return (for example, it updates the 
    <i>ProtocolBindingContext</i> context area). This allows the 
    <i>ProtocolCloseAdapterCompleteEx</i> function to complete the unbind operation.

After the protocol driver calls the 
    <a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a> function, the 
    <i>NdisBindingHandle</i> handle that the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function returned is
    no longer valid. Therefore, 
    <i>ProtocolCloseAdapterCompleteEx</i> cannot call any 
    <b>Ndis<i>Xxx</i></b> functions that require this handle as a parameter.

If the 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function has not already done so,
    <i>ProtocolCloseAdapterCompleteEx</i> can release the resources that the protocol driver allocated for
    per-binding network I/O operations.

If 
    <i>ProtocolUnbindAdapterEx</i> returned NDIS_STATUS_PENDING and saved the 
    <i>UnbindContext</i> handle in the context area at 
    <i>ProtocolBindingContext</i>, 
    <i>ProtocolCloseAdapterCompleteEx</i> can call the 
    <a href="..\ndis\nf-ndis-ndiscompleteunbindadapterex.md">
    NdisCompleteUnbindAdapterEx</a> function to complete the unbinding operation. Consequently, 
    <i>ProtocolCloseAdapterCompleteEx</i> should not release the context area until after it calls 
    <b>NdisCompleteUnbindAdapterEx</b>.

NDIS calls 
    <i>ProtocolCloseAdapterCompleteEx</i> at IRQL = PASSIVE_LEVEL.

To define a <i>ProtocolCloseAdapterCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCloseAdapterCompleteEx</i> function that is named "MyCloseAdapterCompleteEx", use the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscloseadapterex.md">NdisCloseAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscompleteunbindadapterex.md">NdisCompleteUnbindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>