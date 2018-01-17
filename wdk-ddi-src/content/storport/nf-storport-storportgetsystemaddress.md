---
UID: NF:storport.StorPortGetSystemAddress
title: StorPortGetSystemAddress function
author: windows-driver-content
description: The StorPortGetSystemAddress routine returns a virtual address in system space for the data buffer of the specified SCSI request block (SRB).
old-location: storage\storportgetsystemaddress.htm
old-project: storage
ms.assetid: 28bb26bd-7259-4664-8092-6b9a917c1a91
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetSystemAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Server 2003 with SP2.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetSystemAddress
req.alt-loc: storport.h
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetSystemAddress function



## -description
The <b>StorPortGetSystemAddress</b> routine returns a virtual address in system space for the data buffer of the specified SCSI request block (SRB).



## -syntax

````
ULONG StorPortGetSystemAddress(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _Out_ PVOID               *SystemAddress
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> structure.


### -param SystemAddress [out]

A pointer to receive the virtual address of the data buffer.


## -returns
StorPortGetSystemAddress returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the system address was obtained successfully.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>This status code is caused by one of the following conditions:
       

The SRB does not have an associated data buffer.

The pointer to receive the virtual address is <b>NULL</b>.
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>The call was made at an invalid IRQL.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The attempt to map the data buffer to system space failed.

 


## -remarks
Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> or <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetSystemAddress routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

