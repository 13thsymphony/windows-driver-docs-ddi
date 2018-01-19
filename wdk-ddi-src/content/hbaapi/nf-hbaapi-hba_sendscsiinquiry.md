---
UID : NF:hbaapi.HBA_SendScsiInquiry
title : HBA_SendScsiInquiry function
author : windows-driver-content
description : The HBA_SendScsiInquiry routine sends a SCSI inquiry command to the indicated remote port.
old-location : storage\hba_sendscsiinquiry.htm
old-project : storage
ms.assetid : 6239f9b5-99e9-4ed7-b2a8-863c1784692b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : HBA_SendScsiInquiry
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hbaapi.h
req.include-header : Hbaapi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HBA_SendScsiInquiry
req.alt-loc : Hbaapi.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hbaapi.lib
req.dll : Hbaapi.dll
req.irql : 
req.typenames : HBA_WWNTYPE
---


# HBA_SendScsiInquiry function
The <b>HBA_SendScsiInquiry</b> routine sends a SCSI inquiry command to the indicated remote port.

## Syntax

````
HBA_STATUS HBA_API HBA_SendScsiInquiry(
  _In_  HBA_HANDLE handle,
  _In_  HBA_WWN    portWWN,
  _In_  HBA_UINT64 fcLUN,
  _In_  HBA_UINT8  EVPD,
  _In_  HBA_UINT32 PageCode,
  _Out_ void       *pRspBuffer,
  _In_  HBA_UINT32 pRespBufferSize,
  _Out_ void       *pSenseBuffer,
  _In_  HBA_UINT32 SenseBufferSize
);
````

## Parameters

`Handle`



`PortWWN`



`FcLUN`



`EVPD`

Indicates, when 0, that the inquiry command retrieves the standard SCSI inquiry data. When this member is set to 1, it indicates the inquiry command retrieves the vital product data (VPD) specified by <i>PageCode</i>.

`PageCode`

Indicates the VPD page code to retrieve when <i>EVPD</i> is set to 1. If <i>EVPD </i>is not set to 1, <i>PageCode </i>is ignored.

`pRspBuffer`

Pointer to a buffer that receives the output data of the SCSI inquiry command.

`RspBufferSize`



`pSenseBuffer`

Pointer to a buffer that receives the SCSI sense data.

`SenseBufferSize`

On input, indicates the size, in bytes, of the buffer at <i>pSenseBuffer</i>. On output, this member indicates the number of bytes of sense data returned.


## Return Value

The <b>HBA_SendScsiInquiry</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendScsiInquiry</b> returns one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the complete payload of a reply to the SCSI inquiry command was successfully retrieved. 
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_A_TARGET</b></dt>
</dl>Returned if the specified remote port specified by <i>portWWN </i>does not have SCSI target functionality.
<dl>
<dt><b>HBA_STATUS_ERROR_TARGET_BUSY</b></dt>
</dl>Returned if the SCSI inquiry command could not be delivered without causing a SCSI overlapped command condition.
<dl>
<dt><b>HBA_STATUS_SCSI_CHECK_CONDITION</b></dt>
</dl>Returned if a SCSI check condition occurred and SCSI send data is provided in the buffer at <i>pSenseBuffer</i>.
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the execution of the SCSI inquiry command.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendScsiInquiry routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>