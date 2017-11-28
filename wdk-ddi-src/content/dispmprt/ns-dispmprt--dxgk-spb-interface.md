---
UID: NS.dispmprt._DXGK_SPB_INTERFACE
title: DXGK_SPB_INTERFACE
author: windows-driver-content
description: Contains pointers to functions in the Simple Peripheral Bus (SPB) Interface that the display miniport driver can call to inspect and alter SPB resources.
old-location: display\dxgk_spb_interface.htm
old-project: display
ms.assetid: 677619d2-86a1-492e-9964-d50624376ef4
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_SPB_INTERFACE, DXGK_SPB_INTERFACE, *PDXGK_SPB_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_SPB_INTERFACE
req.alt-loc: Dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# DXGK_SPB_INTERFACE structure



## -description
<p>Contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj658947">Simple Peripheral Bus (SPB) Interface</a> that the display miniport driver can call to inspect and alter SPB resources.</p>
<p>For more information on SPB architecture, see <a href="https://msdn.microsoft.com/2c660e14-5b27-4610-a328-735b07ed0773">Simple Peripheral Buses</a> and <a href="https://msdn.microsoft.com/A6DFD2DB-93F4-410F-8875-7E3E3EFCE660">SPB Peripheral Device Driver Overview</a>.</p>


## -syntax

````
typedef struct _DXGK_SPB_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  NTSTATUS               (*OpenSpbResource)(
      _In_ HANDLE DeviceHandle, 
      _In_ LARGE_INTEGER SpbReourceId, 
      _In_opt_ UNICODE_STRING *SpbResourceSubName, 
      _In_ ACCESS_MASK DesiredAccess, 
      _In_ ULONG ShareAccess, 
      _In_ ULONG OpenOptions, 
      _Out_ VOID **SpbResource);
  NTSTATUS               (*CloseSpbResource)(
      _In_ HANDLE DeviceHandle, 
      _In_ VOID *SpbResource);
  NTSTATUS               (*ReadSpbResource)(
      _In_ HANDLE DeviceHandle, 
      _In_ VOID *SpbResource, 
      _In_ ULONG Length, 
      _Out_ VOID *Buffer, 
      _In_opt_ LARGE_INTEGER *ByteOffset, 
      _In_opt_ HANDLE EventHandle, 
      _Out_ IO_STATUS_BLOCK *IoStatusBlock);
  NTSTATUS               (*WriteSpbResource)(
      _In_ HANDLE DeviceHandle, 
      _In_ VOID *SpbResource, 
      _In_ ULONG Length, 
      _In_ VOID *Buffer, 
      _In_opt_ LARGE_INTEGER *ByteOffset, 
      _In_opt_ HANDLE EventHandle, 
      _Out_ IO_STATUS_BLOCK *IoStatusBlock);
  NTSTATUS               (*SpbResourceIoControl)(
      _In_ HANDLE DeviceHandle, 
      _In_ VOID *SpbResource, 
      _In_ ULONG IoControlCode, 
      _In_ ULONG InBufferSize, 
      _In_ VOID *InputBuffer, 
      _In_ ULONG OutBufferSize, 
      _Out_ VOID *OutputBuffer, 
      _In_opt_ HANDLE EventHandle, 
      _Out_ IO_STATUS_BLOCK *IoStatusBlock);
} DXGK_SPB_INTERFACE, *PDXGK_SPB_INTERFACE;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The size, in bytes, of this structure.</p>
</dd>

### -field <b>Version</b>

<dd>
<p>The version number of the SPB interface. Version number constants are defined in Dispmprt.h (for example, DXGK_SPB_INTERFACE_VERSION_1).</p>
</dd>

### -field <b>Context</b>

<dd>
<p>A pointer to a context that is provided by the display miniport driver.</p>
</dd>

### -field <b>InterfaceReference</b>

<dd>
<p>A pointer to an interface reference function that is implemented by the display miniport driver.</p>
</dd>

### -field <b>InterfaceDereference</b>

<dd>
<p>A pointer to an interface dereference function that is implemented by the display miniport driver.</p>
</dd>

### -field <b>OpenSpbResource</b>

<dd>
<p>A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451581">OpenSpbResource</a> function.</p>
</dd>

### -field <b>CloseSpbResource</b>

<dd>
<p>A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406257">CloseSpbResource</a> function.</p>
</dd>

### -field <b>ReadSpbResource</b>

<dd>
<p>A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439824">ReadSpbResource</a> function.</p>
</dd>

### -field <b>WriteSpbResource</b>

<dd>
<p>A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439925">WriteSpbResource</a> function.</p>
</dd>

### -field <b>SpbResourceIoControl</b>

<dd>
<p>A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439861">SpbResourceIoControl</a> function.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406257">CloseSpbResource</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451581">OpenSpbResource</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439824">ReadSpbResource</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439861">SpbResourceIoControl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439925">WriteSpbResource</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_SPB_INTERFACE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
