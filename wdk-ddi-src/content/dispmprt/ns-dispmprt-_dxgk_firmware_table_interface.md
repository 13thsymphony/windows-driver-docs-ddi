---
UID : NS:dispmprt._DXGK_FIRMWARE_TABLE_INTERFACE
title : _DXGK_FIRMWARE_TABLE_INTERFACE
author : windows-driver-content
description : Contains pointers to functions in the System Firmware Table interface that the display miniport driver can call to enumerate and read the system firmware table.
old-location : display\dxgk_firmware_table_interface.htm
old-project : display
ms.assetid : 22ba50eb-e428-433f-aca0-1d61f31fcd0c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_FIRMWARE_TABLE_INTERFACE, *PDXGK_FIRMWARE_TABLE_INTERFACE, DXGK_FIRMWARE_TABLE_INTERFACE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dispmprt.h
req.include-header : Dispmprt.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_FIRMWARE_TABLE_INTERFACE
req.alt-loc : dispmprt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PDXGK_FIRMWARE_TABLE_INTERFACE, DXGK_FIRMWARE_TABLE_INTERFACE"
---

# _DXGK_FIRMWARE_TABLE_INTERFACE structure
Contains pointers to functions in the System Firmware Table interface that the display miniport driver can call to enumerate and read the system firmware table.

## Syntax
````
typedef struct _DXGK_FIRMWARE_TABLE_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  NTSTATUS               (*EnumSystemFirmwareTables)(
      _In_ VOID *Context, 
      _In_ ULONG ProviderSignature, 
      _In_ ULONG BufferSize, 
      _Out_opt_ VOID *Buffer, 
      _Out_ ULONG *RequiredSize);
  NTSTATUS               (*ReadSystemFirmwareTable)(
      _In_ VOID *Context, 
      _In_ ULONG ProviderSignature, 
      _In_ ULONG TableId, 
      _In_ ULONG BufferSize, 
      _Out_opt_ VOID *Buffer, 
      _Out_ ULONG *RequiredSize);
} DXGK_FIRMWARE_TABLE_INTERFACE, *PDXGK_FIRMWARE_TABLE_INTERFACE;
````

## Members

        
            `Context`

            A pointer to a context that is provided by the display port driver.
        
            `EnumSystemFirmwareTables`

            A pointer to the display port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh802466">EnumSystemFirmwareTables</a> function.
        
            `InterfaceDereference`

            A pointer to an interface dereference function that is implemented by the display port driver.
        
            `InterfaceReference`

            A pointer to an interface reference function that is implemented by the display port driver.
        
            `ReadSystemFirmwareTable`

            A pointer to the display port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh802471">ReadSystemFirmwareTable</a> function.
        
            `Size`

            The size, in bytes, of this structure.
        
            `Version`

            The version number of the System Firmware Table interface. Version number constants are defined in Dispmprt.h (for example, <b>DXGK_FIRMWARE_TABLE_INTERFACE_VERSION_1</b>).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h (include Dispmprt.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh802466">EnumSystemFirmwareTables</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh802471">ReadSystemFirmwareTable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_FIRMWARE_TABLE_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>