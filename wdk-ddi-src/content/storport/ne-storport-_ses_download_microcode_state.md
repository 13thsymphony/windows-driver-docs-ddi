---
UID: NE.storport._SES_DOWNLOAD_MICROCODE_STATE
title: _SES_DOWNLOAD_MICROCODE_STATE
author: windows-driver-content
description: TBD.
old-location: storage\ses_download_microcode_state.htm
old-project: storage
ms.assetid: 5edff312-8373-4d36-b93c-c35fe8c2996a
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SES_DOWNLOAD_MICROCODE_STATE, SES_DOWNLOAD_MICROCODE_STATE, *PSES_DOWNLOAD_MICROCODE_STATE, PSES_DOWNLOAD_MICROCODE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: storport.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SES_DOWNLOAD_MICROCODE_STATE
req.alt-loc: scsi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _SES_DOWNLOAD_MICROCODE_STATE enumeration



## -description
TBD



## -syntax

````
typedef enum _SES_DOWNLOAD_MICROCODE_STATE { 
  SesDownloadMcStateNoneInProgress              =  0x00,
  SesDownloadMcStateInProgress                  =  0x01,
  SesDownloadMcStateCompletedPendingReset       =  0x11,
  SesDownloadMcStateCompletedPendingPowerOn     = 0x12,
  SesDownloadMcStateCompletedPendingActivation  = 0x13
} SES_DOWNLOAD_MICROCODE_STATE, *PSES_DOWNLOAD_MICROCODE_STATE;
````


## -enum-fields

### -field SesDownloadMcStateNoneInProgress

Specifies no microcode download operation is in progress.


### -field SesDownloadMcStateInProgress

Specifies a microcode download operation is in progress.


### -field SesDownloadMcStateCompletedPendingReset

Specifies a microcode download operations completed and is waiting for a hard reset.


### -field SesDownloadMcStateCompletedPendingPowerOn

Specifies a microcode download operations completed and is waiting for a power on.


### -field SesDownloadMcStateCompletedPendingActivation

Specifies a microcode download operations completed and is waiting for activation.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 10, version 1709 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Scsi.h (include Minitape.h or Storport.h)</dt>
</dl>
</td>
</tr>
</table>