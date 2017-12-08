---
UID: NF.hbaapi.HBA_SendScsiInquiry
title: HBA_SendScsiInquiry function
author: windows-driver-content
description: The HBA_SendScsiInquiry routine sends a SCSI inquiry command to the indicated remote port.
old-location: storage\hba_sendscsiinquiry.htm
old-project: storage
ms.assetid: 6239f9b5-99e9-4ed7-b2a8-863c1784692b
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_SendScsiInquiry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_SendScsiInquiry
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
---

# HBA_SendScsiInquiry function



## -description
The <b>HBA_SendScsiInquiry</b> routine sends a SCSI inquiry command to the indicated remote port. 


## -syntax

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


## -parameters

### -param handle [in]

Contains a value returned by the routine <a href="storage.hba_openadapter">HBA_OpenAdapter</a> that identifies the HBA on which the target port is located.

### -param portWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the remote target port to which the SCSI inquiry command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 

### -param fcLUN [in]

Indicates the fibre channel logical unit number of the logical unit to which the SCSI inquiry command is sent. 

### -param EVPD [in]

Indicates, when 0, that the inquiry command retrieves the standard SCSI inquiry data. When this member is set to 1, it indicates the inquiry command retrieves the vital product data (VPD) specified by <i>PageCode</i>.

### -param PageCode [in]

Indicates the VPD page code to retrieve when <i>EVPD</i> is set to 1. If <i>EVPD </i>is not set to 1, <i>PageCode </i>is ignored.

### -param pRspBuffer [out]

Pointer to a buffer that receives the output data of the SCSI inquiry command.

### -param pRespBufferSize [in]

Indicates the size, in bytes, of the buffer at <i>pRspBuffer</i>.

### -param pSenseBuffer [out]

Pointer to a buffer that receives the SCSI sense data.

### -param SenseBufferSize [in]

On input, indicates the size, in bytes, of the buffer at <i>pSenseBuffer</i>. On output, this member indicates the number of bytes of sense data returned. 

## -returns
The <b>HBA_SendScsiInquiry</b> routine returns a value of type <a href="storage.hba_status">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendScsiInquiry</b> returns one of the following values.
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

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hba_openadapter">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendScsiInquiry routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
