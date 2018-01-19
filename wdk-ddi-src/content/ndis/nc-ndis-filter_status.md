---
UID : NC:ndis.FILTER_STATUS
title : FILTER_STATUS
author : windows-driver-content
description : The FilterStatus function indicates status changes that are reported by NDIS or an underlying driver.Note  You must declare the function by using the FILTER_STATUS type.
old-location : netvista\filterstatus.htm
old-project : netvista
ms.assetid : 051ce37c-a7a5-4367-9495-023fc51349ba
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
req.alt-api : FilterStatus
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
req.irql : <= DISPATCH_LEVEL
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# FILTER_STATUS function
The
  <i>FilterStatus</i> function indicates status changes that are reported by NDIS or an underlying
  driver.

## Syntax

```
FILTER_STATUS FilterStatus;

void FilterStatus(
  NDIS_HANDLE FilterModuleContext,
  PNDIS_STATUS_INDICATION StatusIndication
)
{...}
```

## Parameters

`FilterModuleContext`

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`StatusIndication`

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## Return Value

None

## Remarks

<i>FilterStatus</i> is an optional function. If a filter driver does not use status indications, it can
    set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function.

To determine link status, use the status indications from underlying drivers instead of OID queries.
    These status indications will improve system performance and avoid possible race conditions.

A filter driver usually calls the 
    <a href="..\ndis\nf-ndis-ndisfindicatestatus.md">NdisFIndicateStatus</a> function at the
    end of its 
    <i>FilterStatus</i> function to pass on the status indication to overlying drivers.

A filter driver can filter out certain status indications or modify the indicated status. To filter
    out a status indication, the driver simply does not call 
    <b>NdisFIndicateStatus</b>.

NDIS calls 
    <i>FilterStatus</i> at IRQL &lt;= DISPATCH_LEVEL.

To define a <i>FilterStatus</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterStatus</i> function that is named "MyStatus", use the <b>FILTER_STATUS</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_STATUS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_STATUS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfindicatestatus.md">NdisFIndicateStatus</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_STATUS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>