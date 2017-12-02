---
UID: NF.ks.KsCreateFilterFactory
title: KsCreateFilterFactory
author: windows-driver-content
description: The KsCreateFilterFactory function adds a filter factory to a given device.
old-location: stream\kscreatefilterfactory.htm
old-project: stream
ms.assetid: ebfdae87-febc-4383-93f4-5d613df273a9
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsCreateFilterFactory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsCreateFilterFactory
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# KsCreateFilterFactory function



## -description
<p>The<b> KsCreateFilterFactory</b> function adds a filter factory to a given device.</p>


## -syntax

````
NTSTATUS KsCreateFilterFactory(
  _In_            PDEVICE_OBJECT          DeviceObject,
  _In_      const KSFILTER_DESCRIPTOR     *Descriptor,
  _In_opt_        PWSTR                   RefString,
  _In_opt_        PSECURITY_DESCRIPTOR    SecurityDescriptor,
  _In_            ULONG                   CreateItemFlags,
  _In_opt_        PFNKSFILTERFACTORYPOWER SleepCallback,
  _In_opt_        PFNKSFILTERFACTORYPOWER WakeCallback,
  _Out_opt_       PKSFILTERFACTORY        *FilterFactory
);
````


## -parameters
<dl>

### -param DeviceObject [in]

<dd>
<p>A pointer to a <a href="..\wdm\ns-wdm--device-object.md">DEVICE_OBJECT</a> structure for which to add a filter factory. </p>
</dd>

### -param Descriptor [in]

<dd>
<p>A pointer to a <a href="..\ks\ns-ks--ksfilter-descriptor.md">KSFILTER_DESCRIPTOR</a> that describes the characteristics of individual filters that this factory can create.</p>
</dd>

### -param RefString [in, optional]

<dd>
<p>If this argument is provided, this string is used as the reference string for filters created by this factory. Otherwise, the reference GUID provided in the descriptor is used.</p>
</dd>

### -param SecurityDescriptor [in, optional]

<dd>
<p>The security descriptor to use in creation of filters by this filter factory. If <b>NULL</b>, no descriptor is provided.</p>
</dd>

### -param CreateItemFlags [in]

<dd>
<p>The following table lists the flags that the minidriver writer uses to specify the characteristics of filters that the new filter factory can create. Set this parameter to the bitwise OR of the flags below.</p>
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>KSCREATE_ITEM_SECURITY_CHANGED</p>
</td>
<td>
<p>Indicates that the security descriptor on this object type has been changed and should be persisted.</p>
</td>
</tr>
<tr>
<td>
<p>KSCREATE_ITEM_WILDCARD</p>
</td>
<td>
<p>Indicates that this create item represents a wildcard that is used for any create requests that do not match any other create items. The ordering of the wildcard entry in the list of create items is irrelevant. Only a single wildcard entry is valid on any list of create items.</p>
</td>
</tr>
<tr>
<td>
<p>KSCREATE_ITEM_NOPARAMETERS</p>
</td>
<td>
<p>Indicates that this create item does not allow any parameters to be passed, and fails if any are found. (Normally, create parameters are passed on to the create handler.) This flag cannot be used with a wildcard flag.</p>
</td>
</tr>
<tr>
<td>
<p>KSCREATE_ITEM_FREEONSTOP</p>
</td>
<td>
<p>Indicates that the create item should be freed when the PnP manager sends <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>. Note that AVStream automatically frees such create items when the device receives PnP stop (<i>after</i> the client has received the PnP stop notification).</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param SleepCallback [in, optional]

<dd>
<p>A pointer to a minidriver-provided routine that receives notifications that the device associated with this filter is going to sleep. Prototype the routine as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void SleepCallback (IN PKSFILTERFACTORY FilterFactory,
    IN DEVICE_POWER_STATE State);</pre>
</td>
</tr>
</table></span></div>
<p>If this parameter is <b>NULL</b>, this filter factory is not notified that the device is going to sleep. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>.</p>
</dd>

### -param WakeCallback [in, optional]

<dd>
<p>A pointer to a minidriver-provided routine that receives notifications that the device associated with this filter is waking up. Prototype the routine as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  void WakeCallback (IN PKSFILTERFACTORY FilterFactory,
    IN DEVICE_POWER_STATE State);</pre>
</td>
</tr>
</table></span></div>
<p>If this parameter is <b>NULL</b>, this filter factory is not notified that the device is waking up. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>. </p>
</dd>

### -param FilterFactory [out, optional]

<dd>
<p>A pointer to a <a href="..\ks\ns-ks--ksfilterfactory.md">KSFILTERFACTORY</a> structure that AVStream sets to point to the newly created filter factory object. If this optional parameter is unspecified, the caller is not informed about the resulting filter factory object.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if the filter factory can be created. Otherwise, it returns an appropriate error code.</p>

## -remarks
<p>If you call <b>KsCreateFilterFactory</b> after <a href="stream.avstrminidevicepoststart">AVStrMiniDevicePostStart</a>), you must then call <a href="..\ks\nf-ks-ksfilterfactorysetdeviceclassesstate.md">KsFilterFactorySetDeviceClassesState</a> to enable the device class. (Also call <b>KsFilterFactorySetDeviceClassesState</b> to disable a filter factory.)</p>

<p>If you call <b>KsCreateFilterFactory</b> in the context of <i>AVStrMiniDevicePostStart</i> or before, you do not need to do this.</p>

<p>Before calling this function, the minidriver must obtain the device mutex. For information about how to do this, see <a href="https://msdn.microsoft.com/cec2a040-59d6-44ef-aef1-04f434811d60">Device Mutex in AVStream</a>.</p>

<p>This function should be used by minidrivers that either initialize themselves without a call to <a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a> or that must dynamically add and remove new filter types. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksdeletefilterfactory.md">KsDeleteFilterFactory</a>
</dt>
<dt>
<a href="..\ks\ns-ks--ksfilter-descriptor.md">KSFILTER_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ks\ns-ks--kspin-descriptor-ex.md">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="..\ks\ns-ks--ksnode-descriptor.md">KSNODE_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateFilterFactory function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
