---
UID: NC:wdfusb.PFN_WDFUSBINTERFACEGETNUMCONFIGUREDPIPES
title: PFN_WDFUSBINTERFACEGETNUMCONFIGUREDPIPES function
author: windows-driver-content
description: The WdfUsbInterfaceGetNumConfiguredPipes method returns the number of pipes that are configured for a specified USB device interface.
old-location: wdf\wdfusbinterfacegetnumconfiguredpipes.htm
old-project: wdf
ms.assetid: dbc929a9-696b-42e1-9888-9e8c0b1e01c9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFUSBINTERFACEGETNUMCONFIGUREDPIPES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfUsbInterfaceGetNumConfiguredPipes
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_TRI_STATE, *PWDF_TRI_STATE
req.product: Windows 10 or later.
---

# PFN_WDFUSBINTERFACEGETNUMCONFIGUREDPIPES function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetNumConfiguredPipes</b> method returns the number of pipes that are configured for a specified USB device interface.



## -syntax

````
BYTE WdfUsbInterfaceGetNumConfiguredPipes(
  _In_ WDFUSBINTERFACE UsbInterface
);
````


## -parameters

### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


## -returns
<b>WdfUsbInterfaceGetNumConfiguredPipes</b> returns the number of pipes that are configured for the specified interface.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Your driver can call <b>WdfUsbInterfaceGetNumConfiguredPipes</b> after it has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>.

For more information about the <b>WdfUsbInterfaceGetNumConfiguredPipes</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example obtains the number of pipes that are configured for a specified USB interface.


## -see-also
<dl>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetNumConfiguredPipes method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

