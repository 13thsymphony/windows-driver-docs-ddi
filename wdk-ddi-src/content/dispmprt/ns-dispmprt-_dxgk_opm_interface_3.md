---
UID : NS:dispmprt._DXGK_OPM_INTERFACE_3
title : _DXGK_OPM_INTERFACE_3
author : windows-driver-content
description : The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location : display\dxgk_opm_interface_3.htm
old-project : display
ms.assetid : 0BD6BA91-7F46-482B-B808-DEB8A23A0B84
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3, *PDXGK_OPM_INTERFACE_3
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dispmprt.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_OPM_INTERFACE_3
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
req.typenames : DXGK_OPM_INTERFACE_3, *PDXGK_OPM_INTERFACE_3
---

# _DXGK_OPM_INTERFACE_3 structure
The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the <a href="https://msdn.microsoft.com/8dc171f7-76ca-4e1a-865e-7dcb6ab9a2e9">Output Protection Manager (OPM) Interface</a>, which is implemented by the display miniport driver.

## Syntax
````
typedef struct _DXGK_OPM_INTERFACE_3 {
  USHORT                                               Size;
  USHORT                                               Version;
  PVOID                                                Context;
  PINTERFACE_REFERENCE                                 InterfaceReference;
  PINTERFACE_DEREFERENCE                               InterfaceDereference;
  DXGKDDI_OPM_GET_CERTIFICATE_SIZE                     DxgkDdiOPMGetCertificateSize;
  DXGKDDI_OPM_GET_CERTIFICATE                          DxgkDdiOPMGetCertificate;
  DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT                  DxgkDdiOPMCreateProtectedOutput;
  DXGKDDI_OPM_GET_RANDOM_NUMBER                        DxgkDdiOPMGetRandomNumber;
  DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS     DxgkDdiOPMSetSigningKeyAndSequenceNumbers;
  DXGKDDI_OPM_GET_INFORMATION                          DxgkDdiOPMGetInformation;
  DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION          DxgkDdiOPMGetCOPPCompatibleInformation;
  DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT               DxgkDdiOPMConfigureProtectedOutput;
  DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT                 DxgkDdiOPMDestroyProtectedOutput;
  DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY DxgkDdiOPMCreateProtectedOutputNonLocalDisplay;
  DXGKDDI_OPM_SET_SRM_LIST                             DxgkDdiOPMSetSrmList;
  DXGKDDI_OPM_GET_SRM_LIST_VERSION                     DxgkDdiOPMGetSrmListVersion;
} DXGK_OPM_INTERFACE_3, *PDXGK_OPM_INTERFACE_3;
````

## Members

        
            `Context`

            A pointer to a private context block. <b>Context</b> must be set to <b>NULL</b>.
        
            `DxgkDdiOPMConfigureProtectedOutput`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function.
        
            `DxgkDdiOPMCreateProtectedOutput`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function.
        
            `DxgkDdiOPMCreateProtectedOutputNonLocalDisplay`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMCreateProtectedOutputNonLocalDisplay</a> function.
        
            `DxgkDdiOPMDestroyProtectedOutput`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMDestroyProtectedOutput</a> function.
        
            `DxgkDdiOPMGetCertificate`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate.md">DxgkDdiOPMGetCertificate</a> function.
        
            `DxgkDdiOPMGetCertificateSize`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a> function.
        
            `DxgkDdiOPMGetCOPPCompatibleInformation`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.
        
            `DxgkDdiOPMGetInformation`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function.
        
            `DxgkDdiOPMGetRandomNumber`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> function.
        
            `DxgkDdiOPMGetSrmListVersion`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMGetSrmListVersion</a> function.
        
            `DxgkDdiOPMSetSigningKeyAndSequenceNumbers`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function.
        
            `DxgkDdiOPMSetSrmList`

            A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMSetSrmList</a> function.
        
            `InterfaceDereference`

            A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.
        
            `InterfaceReference`

            A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.
        
            `Size`

            The size, in bytes, of this structure.
        
            `Version`

            A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The <b>Version</b> member must be set to DXGK_OPM_INTERFACE_VERSION_1, which is defined in Dispmprt.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h |