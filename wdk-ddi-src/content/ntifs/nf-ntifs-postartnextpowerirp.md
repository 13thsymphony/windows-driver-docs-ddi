---
UID: NF:ntifs.PoStartNextPowerIrp
title: PoStartNextPowerIrp function
author: windows-driver-content
description: The PoStartNextPowerIrp routine signals the power manager that the driver is ready to handle the next power IRP. (Windows Server 2003, Windows XP, and Windows 2000 only.).
old-location: kernel\postartnextpowerirp.htm
old-project: kernel
ms.assetid: 92754668-5327-4e37-9da1-cc1870f923c5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoStartNextPowerIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoStartNextPowerIrp
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=DISPATCH_LEVEL
req.typenames: TOKEN_TYPE
---

# PoStartNextPowerIrp function



## -description
The <b>PoStartNextPowerIrp</b> routine signals the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> that the driver is ready to handle the next power <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>. (Windows Server 2003, Windows XP, and Windows 2000 only.)



## -syntax

````
VOID PoStartNextPowerIrp(
  _Inout_ PIRP Irp
);
````


## -parameters

### -param Irp [in, out]

A pointer to an IRP in which the major function code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a>.


## -returns
None


## -remarks
Starting with Windows Vista, the driver is not required to call <b>PoStartNextPowerIrp</b> and a call to this routine does not perform a power management operation. However, on Windows Server 2003, Windows XP, and Windows 2000, <b>PoStartNextPowerIrp</b> must be called by every driver in a device stack after the driver is finished with the previous power IRP, if any, and is ready to handle the next power IRP. It must be called once by each driver for every <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request.

Although power IRPs are completed only once, typically by the bus driver for a device, each driver in the device stack must call <b>PoStartNextPowerIrp</b> as the IRP travels down or back up the stack. Even if a driver fails the IRP, the driver must nevertheless call <b>PoStartNextPowerIrp</b> to signal the power manager that it is ready to handle another power IRP.

The driver must call <b>PoStartNextPowerIrp</b> while the current IRP stack location points to the current driver. Therefore, this routine must be called before <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>, and <a href="..\wdm\nf-wdm-pocalldriver.md">PoCallDriver</a>. As a general rule, a driver should call <b>PoStartNextPowerIrp</b> from its <i>IoCompletion</i> routine associated with the IRP or from the callback routine it passed to <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>.

Bus drivers must call <b>PoStartNextPowerIrp</b> before completing each IRP.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pocalldriver.md">PoCallDriver</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoStartNextPowerIrp routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

