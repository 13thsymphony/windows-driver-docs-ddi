---
UID : NC:dot11wdi.MINIPORT_WDI_STOP_ADAPTER_OPERATION
title : MINIPORT_WDI_STOP_ADAPTER_OPERATION
author : windows-driver-content
description : The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in MiniportWdiStartAdapterOperation.
old-location : netvista\miniportwdistopoperation.htm
old-project : netvista
ms.assetid : 19BDA96D-DA25-4555-B836-78F4695257B0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _SYNTH_STATS, SYNTH_STATS, *PSYNTH_STATS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dot11wdi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : (*MINIPORT_WDI_STOP_OPERATION_HANDLER)
req.alt-loc : dot11wdi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_STOP_ADAPTER_OPERATION callback function
The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_start_adapter_operation.md">MiniportWdiStartAdapterOperation</a>.

This is an optional WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

## Syntax

```
MINIPORT_WDI_STOP_ADAPTER_OPERATION MiniportWdiStopAdapterOperation;

void MiniportWdiStopAdapterOperation(
  NDIS_HANDLE MiniportAdapterContext
)
{...}
```

## Parameters

`MiniportAdapterContext`

The handle to the context area that the miniport driver allocated.


## Return Value

This callback function does not return a value.

To define a MiniportWdiStopAdapterOperation function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiStopAdapterOperation function that is named "MyStopOperation", use the <b>MINIPORT_WDI_STOP_ADAPTER_OPERATION</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_STOP_ADAPTER_OPERATION</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_STOP_ADAPTER_OPERATION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dot11wdi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_start_adapter_operation.md">MiniportWdiStartOperation</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_STOP_ADAPTER_OPERATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>