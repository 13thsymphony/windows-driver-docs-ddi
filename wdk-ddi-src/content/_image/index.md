---
UID: TP:image
ms.assetid: 7b3b278b-3cff-355c-a263-9be80b8afde3
ms.author: windowsdriverdev
ms.date: 01/19/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Imaging devices


Overview of the Imaging devices technology.

To develop Imaging devices, you need these headers:

 * [ptpusd.h](..\ptpusd\index.md)
 * [scsiscan.h](..\scsiscan\index.md)
 * [sti.h](..\sti\index.md)
 * [stiusd.h](..\stiusd\index.md)
 * [usbscan.h](..\usbscan\index.md)
 * [wia_lh.h](..\wia_lh\index.md)
 * [wiadef.h](..\wiadef\index.md)
 * [wiadevd.h](..\wiadevd\index.md)
 * [wiamdef.h](..\wiamdef\index.md)
 * [wiamicro.h](..\wiamicro\index.md)
 * [wiamindr_lh.h](..\wiamindr_lh\index.md)
 * [wiatwcmp.h](..\wiatwcmp\index.md)
 * [wiautil.h](..\wiautil\index.md)

For the programming guide, see [Imaging devices](https://docs.microsoft.com/en-us/windows-hardware/drivers/image).

## Functions

| Title   | Description   |
| ---- |:---- |
| [MicroEntry function](..\wiamicro\nf-wiamicro-microentry.md) | The MicroEntry function responds to commands sent by the WIA Flatbed driver. |
| [Scan function](..\wiamicro\nf-wiamicro-scan.md) | The Scan function reads data from the device and returns the data to the WIA Flatbed driver. |
| [SetPixelWindow function](..\wiamicro\nf-wiamicro-setpixelwindow.md) | The SetPixelWindow function sets the image area to be scanned. |
| [wiasCreateChildAppItem function](..\wiamdef\nf-wiamdef-wiascreatechildappitem.md) | The wiasCreateChildAppItem function creates a new application item and inserts it as a child of the specified (parent) item. Note that this item will not have any properties in its property sets until the driver or application actually fills them in. |
| [wiasCreateDrvItem function](..\wiamdef\nf-wiamdef-wiascreatedrvitem.md) | The wiasCreateDrvItem function creates an IWiaDrvItem Interface object. |
| [wiasCreateLogInstance function](..\wiamdef\nf-wiamdef-wiascreateloginstance.md) | The wiasCreateLogInstance function creates an instance of a logging object. |
| [wiasCreatePropContext function](..\wiamdef\nf-wiamdef-wiascreatepropcontext.md) | The wiasCreatePropContext function allocates a property context to indicate which of an item's properties are being changed by the application. |
| [wiasDebugError function](..\wiamdef\nf-wiamdef-wiasdebugerror.md) | This function prints a debug error string in the Device Manager debug console. The output color is always red. |
| [wiasDebugTrace function](..\wiamdef\nf-wiamdef-wiasdebugtrace.md) | This function prints a debug trace string in the Device Manager debug console. |
| [wiasDownSampleBuffer function](..\wiamdef\nf-wiamdef-wiasdownsamplebuffer.md) | The wiasDownSampleBuffer function takes in a buffer of DWORD-aligned pixel data and downsamples it (produces image data of lower resolution) to the specified size and resolution. |
| [wiasFormatArgs function](..\wiamdef\nf-wiamdef-wiasformatargs.md) | The wiasFormatArgs function formats an argument list into a packaged string for logging. |
| [wiasFreePropContext function](..\wiamdef\nf-wiamdef-wiasfreepropcontext.md) | The wiasFreePropContext function releases the memory occupied by a WIA_PROPERTY_CONTEXT structure. |
| [wiasGetChangedValueFloat function](..\wiamdef\nf-wiamdef-wiasgetchangedvaluefloat.md) | The wiasGetChangedValueFloat function determines whether a property with a floating-point value has been changed by an application. |
| [wiasGetChangedValueGuid function](..\wiamdef\nf-wiamdef-wiasgetchangedvalueguid.md) | The wiasGetChangedValueGuid function determines whether a property with a GUID value has been changed by an application. |
| [wiasGetChangedValueLong function](..\wiamdef\nf-wiamdef-wiasgetchangedvaluelong.md) | The wiasGetChangedValueLong function determines whether a property with a long integer value has been changed by an application. |
| [wiasGetChangedValueStr function](..\wiamdef\nf-wiamdef-wiasgetchangedvaluestr.md) | The wiasGetChangedValueStr function determines whether a property with a string value has been changed by an application. |
| [wiasGetChildrenContexts function](..\wiamdef\nf-wiamdef-wiasgetchildrencontexts.md) | The wiasGetChildrenContexts function retrieves an array of item contexts belonging to the current item's children. |
| [wiasGetContextFromName function](..\wiamdef\nf-wiamdef-wiasgetcontextfromname.md) | The wiasGetContextFromName function retrieves the item context for an item name. |
| [wiasGetDrvItem function](..\wiamdef\nf-wiamdef-wiasgetdrvitem.md) | The wiasGetDrvItem function retrieves a driver item. |
| [wiasGetImageInformation function](..\wiamdef\nf-wiamdef-wiasgetimageinformation.md) | The wiasGetImageInformation function retrieves transfer context information from an item. |
| [wiasGetItemType function](..\wiamdef\nf-wiamdef-wiasgetitemtype.md) | The wiasGetItemType function indicates the item type. |
| [wiasGetPropertyAttributes function](..\wiamdef\nf-wiamdef-wiasgetpropertyattributes.md) | The wiasGetPropertyAttributes function retrieves the access flags and valid values for a set of properties. |
| [wiasGetRootItem function](..\wiamdef\nf-wiamdef-wiasgetrootitem.md) | The wiasGetRootItem function retrieves the root item context of a specified WIA item. |
| [wiasIsPropChanged function](..\wiamdef\nf-wiamdef-wiasispropchanged.md) | The wiasIsPropChanged function tests whether a specified property has been changed by an application. |
| [wiasParseEndorserString function](..\wiamdef\nf-wiamdef-wiasparseendorserstring.md) | The wiasParseEndorserString function parses an endorser string, replacing WIA service-defined and vendor-defined tokens in the string with values associated with those tokens. |
| [wiasPrintDebugHResult function](..\wiamdef\nf-wiamdef-wiasprintdebughresult.md) | The wiasPrintDebugHResult function is obsolete for Windows XP and later, and is no longer supported. Use the WIAS_LHRESULT macro instead.This function prints an HRESULT string on the Device Manager debug console. |
| [wiasQueueEvent function](..\wiamdef\nf-wiamdef-wiasqueueevent.md) | The wiasQueueEvent function informs the service that the device generated an event. |
| [wiasReadMultiple function](..\wiamdef\nf-wiamdef-wiasreadmultiple.md) | The wiasReadMultiple function retrieves multiple property values from a WIA item. |
| [wiasReadPropBin function](..\wiamdef\nf-wiamdef-wiasreadpropbin.md) | The wiasReadPropBin function retrieves a binary-data property value from a WIA item. |
| [wiasReadPropFloat function](..\wiamdef\nf-wiamdef-wiasreadpropfloat.md) | The wiasReadPropFloat function retrieves a floating-point property value from a WIA item. |
| [wiasReadPropGuid function](..\wiamdef\nf-wiamdef-wiasreadpropguid.md) | The wiasReadPropGuid function retrieves a GUID property value from a WIA item. |
| [wiasReadPropLong function](..\wiamdef\nf-wiamdef-wiasreadproplong.md) | The wiasReadPropLong function retrieves a long integer property value from a WIA item. |
| [wiasReadPropStr function](..\wiamdef\nf-wiamdef-wiasreadpropstr.md) | The wiasReadPropStr function retrieves a string property value from a WIA item. |
| [wiasSendEndOfPage function](..\wiamdef\nf-wiamdef-wiassendendofpage.md) | The wiasSendEndOfPage function calls the client callback routine during a data transfer, sending the current total page count. |
| [wiasSetItemPropAttribs function](..\wiamdef\nf-wiamdef-wiassetitempropattribs.md) | The wiasSetItemPropAttribs function sets the access flags and valid values for an item's set of properties. |
| [wiasSetItemPropNames function](..\wiamdef\nf-wiamdef-wiassetitempropnames.md) | The wiasSetItemPropNames function writes property names to item properties. |
| [wiasSetPropChanged function](..\wiamdef\nf-wiamdef-wiassetpropchanged.md) | The wiasSetPropChanged function modifies a property context to indicate that a property is being changed. |
| [wiasSetPropertyAttributes function](..\wiamdef\nf-wiamdef-wiassetpropertyattributes.md) | The wiasSetPropertyAttributes function sets the access flags and valid values for a set of properties. |
| [wiasSetValidFlag function](..\wiamdef\nf-wiamdef-wiassetvalidflag.md) | The wiasSetValidFlag function sets the valid values for a WIA_PROP_FLAG property. |
| [wiasSetValidListFloat function](..\wiamdef\nf-wiamdef-wiassetvalidlistfloat.md) | The wiasSetValidListFloat function sets valid values for a WIA_PROP_LIST property of type VT_R4. |
| [wiasSetValidListGuid function](..\wiamdef\nf-wiamdef-wiassetvalidlistguid.md) | The wiasSetValidListGuid function sets valid values for a WIA_PROP_LIST property of type VT_CLSID. |
| [wiasSetValidListLong function](..\wiamdef\nf-wiamdef-wiassetvalidlistlong.md) | The wiasSetValidListLong function sets the valid values for a WIA_PROP_LIST property of type VT_I4. |
| [wiasSetValidListStr function](..\wiamdef\nf-wiamdef-wiassetvalidliststr.md) | The wiasSetValidListStr function sets the valid values for a WIA_PROP_LIST property of type VT_BSTR. |
| [wiasSetValidRangeFloat function](..\wiamdef\nf-wiamdef-wiassetvalidrangefloat.md) | The wiasSetValidRangeFloat function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_R4. |
| [wiasSetValidRangeLong function](..\wiamdef\nf-wiamdef-wiassetvalidrangelong.md) | The wiasSetValidRangeLong function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_I4. |
| [wiasUpdateScanRect function](..\wiamdef\nf-wiamdef-wiasupdatescanrect.md) | The wiasUpdateScanRect function updates the scanning area sizes of the scanning device. |
| [wiasUpdateValidFormat function](..\wiamdef\nf-wiamdef-wiasupdatevalidformat.md) | The wiasUpdateValidFormat function updates the valid format of the property context for the current minidriver. |
| [wiasValidateItemProperties function](..\wiamdef\nf-wiamdef-wiasvalidateitemproperties.md) | The wiasValidateItemProperties function validates a list of simple item properties against their current valid values. |
| [wiasWriteBufToFile function](..\wiamdef\nf-wiamdef-wiaswritebuftofile.md) | The wiasWriteBufToFile function writes from a specified buffer to an image file. |
| [wiasWriteMultiple function](..\wiamdef\nf-wiamdef-wiaswritemultiple.md) | The wiasWriteMultiple function writes multiple property values to a WIA item. |
| [wiasWritePageBufToFile function](..\wiamdef\nf-wiamdef-wiaswritepagebuftofile.md) | The wiasWritePageBufToFile function writes the contents of a temporary page buffer to an image file. |
| [wiasWritePageBufToStream function](..\wiamdef\nf-wiamdef-wiaswritepagebuftostream.md) | The wiasWritePageBufToStream function writes the contents of a temporary page buffer to the IStream interface provided by the application. |
| [wiasWritePropBin function](..\wiamdef\nf-wiamdef-wiaswritepropbin.md) | The wiasWritePropBin function writes a single binary-data property value to a WIA item. |
| [wiasWritePropFloat function](..\wiamdef\nf-wiamdef-wiaswritepropfloat.md) | The wiasWritePropFloat function writes a single floating-point property value to a WIA item. |
| [wiasWritePropGuid function](..\wiamdef\nf-wiamdef-wiaswritepropguid.md) | The wiasWritePropGuid function writes a single GUID property value to a WIA item. |
| [wiasWritePropLong function](..\wiamdef\nf-wiamdef-wiaswriteproplong.md) | The wiasWritePropLong function writes a single long integer property value to a WIA item. |
| [wiasWritePropStr function](..\wiamdef\nf-wiamdef-wiaswritepropstr.md) | The wiasWritePropStr function writes a single string property value to a WIA item. |
| [wiauDbgDump function](..\wiautil\nf-wiautil-wiaudbgdump.md) | The wiauDbgDump function logs a message containing one or more data values. |
| [wiauDbgError function](..\wiautil\nf-wiautil-wiaudbgerror.md) | The wiauDbgError function logs an error message. |
| [wiauDbgErrorHr function](..\wiautil\nf-wiautil-wiaudbgerrorhr.md) | The wiauDbgErrorHr function logs a message containing an HRESULT and its error message string. |
| [wiauDbgFlags function](..\wiautil\nf-wiautil-wiaudbgflags.md) | The wiauDbgFlags function determines whether a particular debugging flag is set. |
| [wiauDbgHelper function](..\wiautil\nf-wiautil-wiaudbghelper.md) | The wiauDbgHelper function formats a message and writes it to a log file, or debugger, or both. |
| [wiauDbgHelper2 function](..\wiautil\nf-wiautil-wiaudbghelper2.md) | The wiauDbgHelper2 function writes a message to a log file, or debugger, or both. |
| [wiauDbgInit function](..\wiautil\nf-wiautil-wiaudbginit.md) | The wiauDbgInit function initializes WIA debugging. |
| [wiauDbgLegacyError function](..\wiautil\nf-wiautil-wiaudbglegacyerror.md) | The wiauDbgLegacyError function logs an error message. |
| [wiauDbgLegacyError2 function](..\wiautil\nf-wiautil-wiaudbglegacyerror2.md) | The wiauDbgLegacyError2 function logs an error message. |
| [wiauDbgLegacyHresult2 function](..\wiautil\nf-wiautil-wiaudbglegacyhresult2.md) | The wiauDbgLegacyHresult2 function logs a default message containing an HRESULT. |
| [wiauDbgLegacyTrace function](..\wiautil\nf-wiautil-wiaudbglegacytrace.md) | The wiauDbgLegacyTrace function logs a trace message. |
| [wiauDbgLegacyTrace2 function](..\wiautil\nf-wiautil-wiaudbglegacytrace2.md) | The wiauDbgLegacyTrace2 function logs a trace message. |
| [wiauDbgLegacyWarning function](..\wiautil\nf-wiautil-wiaudbglegacywarning.md) | The wiauDbgLegacyWarning function logs a warning message. |
| [wiauDbgSetFlags function](..\wiautil\nf-wiautil-wiaudbgsetflags.md) | The wiauDbgSetFlags function sets debugging flags. |
| [wiauDbgTrace function](..\wiautil\nf-wiautil-wiaudbgtrace.md) | The wiauDbgTrace function logs a trace message. |
| [wiauDbgWarning function](..\wiautil\nf-wiautil-wiaudbgwarning.md) | The wiauDbgWarning function logs a warning message. |
| [wiauGetDrvItemContext function](..\wiautil\nf-wiautil-wiaugetdrvitemcontext.md) | The wiauGetDrvItemContext function gets the driver item context, and optionally, the driver item. |
| [wiauGetResourceString function](..\wiautil\nf-wiautil-wiaugetresourcestring.md) | The wiauGetResourceString function gets a resource string, storing it as a BSTR. |
| [wiauGetValidFormats function](..\wiautil\nf-wiautil-wiaugetvalidformats.md) | The wiauGetValidFormats function calls the IWiaMiniDrv |
| [wiauPropInPropSpec function](..\wiautil\nf-wiautil-wiaupropinpropspec.md) | The wiauPropInPropSpec function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found. |
| [wiauPropsInPropSpec function](..\wiautil\nf-wiautil-wiaupropsinpropspec.md) | The wiauPropsInPropSpec function determines whether any of a list of property specification IDs is contained within an array of such values. |
| [wiauSetImageItemSize function](..\wiautil\nf-wiautil-wiausetimageitemsize.md) | The wiauSetImageItemSize function calculates the size and width, in bytes, for an image, based on the current WIA_IPA_FORMAT setting (described in the Microsoft Windows SDK documentation), and writes the new values to the appropriate properties. |
| [wiauStrC2C function](..\wiautil\nf-wiautil-wiaustrc2c.md) | The wiauStrC2C function copies an ANSI character string to another ANSI character string. |
| [wiauStrC2W function](..\wiautil\nf-wiautil-wiaustrc2w.md) | The wiauStrC2W function converts an ANSI character string to a Unicode string. |
| [wiauStrW2C function](..\wiautil\nf-wiautil-wiaustrw2c.md) | The wiauStrW2C function converts a Unicode string to an ANSI character string. |
| [wiauStrW2W function](..\wiautil\nf-wiautil-wiaustrw2w.md) | The wiauStrW2W function copies a Unicode string to another Unicode string. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [VAL structure](..\wiamicro\ns-wiamicro-val.md) | The VAL structure is used by the microdriver and WIA Flatbed driver to pass information between each other. |
| [_BMP_IMAGE_INFO structure](..\wiautil\ns-wiautil-_bmp_image_info.md) | The BMP_IMAGE_INFO structure contains information about a BMP image. |
| [_CHANNEL_INFO structure](..\usbscan\ns-usbscan-_channel_info.md) | The CHANNEL_INFO structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_CHANNEL_ALIGN_RQST. |
| [_DEVICE_DESCRIPTOR structure](..\usbscan\ns-usbscan-_device_descriptor.md) | The DEVICE_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_DEVICE_DESCRIPTOR. |
| [_DRV_VERSION structure](..\usbscan\ns-usbscan-_drv_version.md) | The DRV_VERSION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_VERSION. |
| [_ERROR_INFOW structure](..\sti\ns-sti-_error_infow.md) | The STI_ERROR_INFO structure is used as a parameter for the IStiDevice |
| [_IO_BLOCK structure](..\usbscan\ns-usbscan-_io_block.md) | The IO_BLOCK structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_READ_REGISTERS or IOCTL_WRITE_REGISTERS. |
| [_IO_BLOCK_EX structure](..\usbscan\ns-usbscan-_io_block_ex.md) | The IO_BLOCK_EX structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SEND_USB_REQUEST. |
| [_MINIDRV_TRANSFER_CONTEXT structure](..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md) | The MINIDRV_TRANSFER_CONTEXT structure is used to store image and other information needed for a memory-callback data transfer or a file data transfer. |
| [_PTP_VENDOR_DATA_IN structure](..\ptpusd\ns-ptpusd-_ptp_vendor_data_in.md) | The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device. |
| [_PTP_VENDOR_DATA_OUT structure](..\ptpusd\ns-ptpusd-_ptp_vendor_data_out.md) | The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device. |
| [_RANGEVALUE structure](..\wiamicro\ns-wiamicro-_rangevalue.md) | The RANGEVALUE structure is used by a microdriver to communicate to the WIA Flatbed driver the legal values for a microdriver function parameter. |
| [_SCANINFO structure](..\wiamicro\ns-wiamicro-_scaninfo.md) | The SCANINFO structure is used to store and communicate information about a scan acquisition. |
| [_SCANWINDOW structure](..\wiamicro\ns-wiamicro-_scanwindow.md) | The SCANWINDOW structure is used by the WIA Flatbed driver to tell the microdriver what image area to scan. |
| [_SCSISCAN_CMD structure](..\scsiscan\ns-scsiscan-_scsiscan_cmd.md) | The SCSISCAN_CMD structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SCSISCAN_CMD. |
| [_SCSISCAN_INFO structure](..\scsiscan\ns-scsiscan-_scsiscan_info.md) | The SCSISCAN_INFO structure is used as a parameter to DeviceIoControl (described in the Microsoft Windows SDK documentation), when the specified I/O control code is IOCTL_SCSISCAN_GET_INFO. |
| [_STINOTIFY structure](..\sti\ns-sti-_stinotify.md) | The STINOTIFY structure is used as a parameter to the IStillImage |
| [_STISUBSCRIBE structure](..\sti\ns-sti-_stisubscribe.md) | The STISUBSCRIBE structure is used as a parameter for the IStiDevice |
| [_STI_DEVICE_INFORMATIONW structure](..\sti\ns-sti-_sti_device_informationw.md) | The STI_DEVICE_INFORMATION structure is used as an output parameter for the IStillImage |
| [_STI_DEVICE_STATUS structure](..\sti\ns-sti-_sti_device_status.md) | The STI_DEVICE_STATUS structure is used as a parameter to the IStiDevice |
| [_STI_DEV_CAPS structure](..\sti\ns-sti-_sti_dev_caps.md) | The STI_DEV_CAPS structure is used as a parameter to the IStiDevice |
| [_STI_DIAG structure](..\sti\ns-sti-_sti_diag.md) | The STI_DIAG structure is used as a parameter to the IStiDevice |
| [_STI_USD_CAPS structure](..\stiusd\ns-stiusd-_sti_usd_caps.md) | The STI_USD_CAPS structure is used as a parameter for the IStiUSD |
| [_STI_WIA_DEVICE_INFORMATIONW structure](..\sti\ns-sti-_sti_wia_device_informationw.md) | The STI_WIA_DEVICE_INFORMATION structure contains device information. |
| [_TWAIN_CAPABILITY structure](..\wiatwcmp\ns-wiatwcmp-_twain_capability.md) | The TWAIN_CAPABILITY structure holds information used when a TWAIN-compatible application communicates with a WIA driver. |
| [_USBSCAN_GET_DESCRIPTOR structure](..\usbscan\ns-usbscan-_usbscan_get_descriptor.md) | The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_USB_DESCRIPTOR. |
| [_USBSCAN_PIPE_CONFIGURATION structure](..\usbscan\ns-usbscan-_usbscan_pipe_configuration.md) | The USBSCAN_PIPE_CONFIGURATION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_PIPE_CONFIGURATION. |
| [_USBSCAN_PIPE_INFORMATION structure](..\usbscan\ns-usbscan-_usbscan_pipe_information.md) | The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a USBSCAN_PIPE_CONFIGURATION structure. |
| [_USBSCAN_TIMEOUT structure](..\usbscan\ns-usbscan-_usbscan_timeout.md) | The USBSCAN_TIMEOUT structure stores time-out values for USB bulk IN and bulk OUT operations, and interrupts. |
| [_WIAS_CHANGED_VALUE_INFO structure](..\wiamindr_lh\ns-wiamindr_lh-_wias_changed_value_info.md) | The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property. |
| [_WIAS_DOWN_SAMPLE_INFO structure](..\wiamindr_lh\ns-wiamindr_lh-_wias_down_sample_info.md) | The WIAS_DOWN_SAMPLE_INFO structure stores information used by the downsampling helper function, wiasDownSampleBuffer. |
| [_WIAS_ENDORSER_INFO structure](..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_info.md) | The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs. |
| [_WIAS_ENDORSER_VALUE structure](..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_value.md) | The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings. |
| [_WIA_BARCODES structure](..\wiadef\ns-wiadef-_wia_barcodes.md) | The WIA_BARCODES structure stores header information for the barcode metadata report of one scan job (one call to IWiaMiniDrv |
| [_WIA_BARCODE_INFO structure](..\wiadef\ns-wiadef-_wia_barcode_info.md) | The WIA_BARCODE_INFO structure stores information for one decoded barcode. |
| [_WIA_DEV_CAP_DRV structure](..\wiamindr_lh\ns-wiamindr_lh-_wia_dev_cap_drv.md) | The WIA_DEV_CAP_DRV structure is used to enumerate device capabilities. A device capability is defined by an event or command that the device supports. |
| [_WIA_MICR structure](..\wiadef\ns-wiadef-_wia_micr.md) | The WIA_MICR structure stores header information for the MICR metadata report of one scan job (one call to IWiaMiniDrv |
| [_WIA_MICR_INFO structure](..\wiadef\ns-wiadef-_wia_micr_info.md) | The WIA_MICR_INFO structure stores information for one decoded MICR code. |
| [_WIA_PATCH_CODES structure](..\wiadef\ns-wiadef-_wia_patch_codes.md) | The WIA_PATCH_CODES structure stores header information for the patch code metadata report of one scan job (one call to IWiaMiniDrv |
| [_WIA_PATCH_CODE_INFO structure](..\wiadef\ns-wiadef-_wia_patch_code_info.md) | The WIA_PATCH_CODE_INFO structure stores information for one decoded patch code. |
| [_WIA_PROPERTY_CONTEXT structure](..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md) | The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context. |
| [_WIA_PROPERTY_INFO structure](..\wiamindr_lh\ns-wiamindr_lh-_wia_property_info.md) | The WIA_PROPERTY_INFO structure is used to store default access and valid value information for an item property of arbitrary type. |
| [tagDEVICEDIALOGDATA structure](..\wiadevd\ns-wiadevd-tagdevicedialogdata.md) | The DEVICEDIALOGDATA structure contains all the data needed to implement a custom device dialog. |
| [tagDEVICEDIALOGDATA2 structure](..\wiadevd\ns-wiadevd-tagdevicedialogdata2.md) | The DEVICEDIALOGDATA2 structure contains all the data needed to implement a custom device dialog. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [PIPE_TYPE Enumeration](..\usbscan\ne-usbscan-pipe_type.md) | The PIPE_TYPE data type is used as input to the DeviceIoControl function, if the I/O control code is IOCTL_CANCEL_IO or IOCTL_RESET_PIPE. |
| [SKIP_AMOUNT Enumeration](..\wiautil\ne-wiautil-skip_amount.md) | The SKIP_AMOUNT enumeration is used to indicate whether the file and informational headers of an image should be skipped over. |
| [_RAW_PIPE_TYPE Enumeration](..\usbscan\ne-usbscan-_raw_pipe_type.md) | The RAW_PIPE_TYPE data type is used to specify the type of a USB pipe. |
| [_STI_DEVICE_MJ_TYPE Enumeration](..\sti\ne-sti-_sti_device_mj_type.md) | The STI_DEVICE_TYPE type identifies the device type of a still image device.The DWORD is divided into a HIWORD containing the major device type, and a LOWORD containing a vendor-defined subtype. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_CANCEL_IO IOCTL](..\usbscan\ni-usbscan-ioctl_cancel_io.md) | Cancels activity on the specified USB transfer pipe that is associated with the specified device handle. |
| [IOCTL_GET_CHANNEL_ALIGN_RQST IOCTL](..\usbscan\ni-usbscan-ioctl_get_channel_align_rqst.md) | Returns a USB device's maximum packet size for the read, write, and interrupt transfer pipes associated with the specified device handle. |
| [IOCTL_GET_DEVICE_DESCRIPTOR IOCTL](..\usbscan\ni-usbscan-ioctl_get_device_descriptor.md) | Returns vendor and device identifiers. |
| [IOCTL_GET_PIPE_CONFIGURATION IOCTL](..\usbscan\ni-usbscan-ioctl_get_pipe_configuration.md) | Returns a description of every transfer pipe supported for a device. |
| [IOCTL_GET_USB_DESCRIPTOR IOCTL](..\usbscan\ni-usbscan-ioctl_get_usb_descriptor.md) | Returns a specified USB Descriptor. |
| [IOCTL_GET_VERSION IOCTL](..\usbscan\ni-usbscan-ioctl_get_version.md) | Returns the version number of the driver. |
| [IOCTL_READ_REGISTERS IOCTL](..\usbscan\ni-usbscan-ioctl_read_registers.md) | Reads from USB device registers, using the control pipe. |
| [IOCTL_RESET_PIPE IOCTL](..\usbscan\ni-usbscan-ioctl_reset_pipe.md) | Resets the specified USB transfer pipe that is associated with the specified device handle. |
| [IOCTL_SCSISCAN_CMD IOCTL](..\scsiscan\ni-scsiscan-ioctl_scsiscan_cmd.md) | Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses. |
| [IOCTL_SCSISCAN_GET_INFO IOCTL](..\scsiscan\ni-scsiscan-ioctl_scsiscan_get_info.md) | The IOCTL_SCSISCAN_GET_INFO I/O control code returns device information. |
| [IOCTL_SCSISCAN_LOCKDEVICE IOCTL](..\scsiscan\ni-scsiscan-ioctl_scsiscan_lockdevice.md) | Reserved for use by Microsoft. |
| [IOCTL_SCSISCAN_SET_TIMEOUT IOCTL](..\scsiscan\ni-scsiscan-ioctl_scsiscan_set_timeout.md) | The IOCTL_SCSISCAN_SET_TIMEOUT control code modifies the time-out value used by the kernel-mode still image driver for SCSI buses when it accesses a device. |
| [IOCTL_SCSISCAN_UNLOCKDEVICE IOCTL](..\scsiscan\ni-scsiscan-ioctl_scsiscan_unlockdevice.md) | Reserved for use by Microsoft. |
| [IOCTL_SEND_USB_REQUEST IOCTL](..\usbscan\ni-usbscan-ioctl_send_usb_request.md) | Sends a vendor-defined request to a USB device, using the control pipe, and optionally sends or receives additional data. |
| [IOCTL_SET_TIMEOUT IOCTL](..\usbscan\ni-usbscan-ioctl_set_timeout.md) | Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access. |
| [IOCTL_WAIT_ON_DEVICE_EVENT IOCTL](..\usbscan\ni-usbscan-ioctl_wait_on_device_event.md) | Returns information about an event occurring on a USB interrupt pipe. |
| [IOCTL_WRITE_REGISTERS IOCTL](..\usbscan\ni-usbscan-ioctl_write_registers.md) | Writes to USB device registers, using the control pipe. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWiaDrvItem interface](..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md) | The IWiaDrvItem interface provides methods that a WIA minidriver can use to manage a tree of IWiaDrvItem items. |
| [IWiaErrorHandler interface](..\wia_lh\nn-wia_lh-iwiaerrorhandler.md) | The IWiaErrorHandler interface provides the GetStatusDescription and ReportStatus methods, which enable minidrivers to give users information about status or errors during a data transfer and possibly give an opportunity to recover from errors. |
| [IWiaImageFilter interface](..\wia_lh\nn-wia_lh-iwiaimagefilter.md) | The IWiaImageFilter interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA). |
| [IWiaLog interface](..\wia_lh\nn-wia_lh-iwialog.md) | The IWiaLog interface provides methods to enable minidrivers to log trace, error, and warning messages to the diagnostic log file Wiaservc.log. |
| [IWiaMiniDrv interface](..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md) | The IWiaMiniDrv interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device. |
| [IWiaMiniDrvCallBack interface](..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrvcallback.md) | The IWiaMiniDrvCallBack interface provides the MiniDrvCallback method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service. |
| [IWiaMiniDrvTransferCallback interface](..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrvtransfercallback.md) | This is a Callback interface that is called by the WIA mini-driver for stream-based transfers. |
| [IWiaSegmentationFilter interface](..\wia_lh\nn-wia_lh-iwiasegmentationfilter.md) | The IWiaSegmentationFilter interface provides the DetectRegions method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later. |
| [IWiaTransferCallback interface](..\wia_lh\nn-wia_lh-iwiatransfercallback.md) | The IWiaTransferCallback interface is implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA). |

## Macros

| Title   | Description   |
| ---- |:---- |
| [WIAS_ASSERT function](..\wiamdef\nf-wiamdef-wias_assert.md) | The WIAS_ASSERT macro writes a diagnostic message to the Wiatrace.log file. |
| [WIAS_ERROR function](..\wiamdef\nf-wiamdef-wias_error.md) | The WIAS_ERROR macro writes a diagnostic message to the Wiatrace.log file. |
| [WIAS_HRESULT function](..\wiamdef\nf-wiamdef-wias_hresult.md) | The WIAS_HRESULT macro writes a diagnostic message to the Wiatrace.log file. |
| [WIAS_LERROR function](..\wiamdef\nf-wiamdef-wias_lerror.md) | The WIAS_LERROR macro is obsolete for Windows Vista and later. It is recommended that the WIAS_ERROR macro be used instead.The WIAS_LERROR macro writes a diagnostic WIA_ERROR message to the log file. |
| [WIAS_LHRESULT function](..\wiamdef\nf-wiamdef-wias_lhresult.md) | The WIAS_LHRESULT macro is obsolete for Windows Vista and later. It is recommended that the WIAS_HRESULT macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file. |
| [WIAS_LTRACE function](..\wiamdef\nf-wiamdef-wias_ltrace.md) | The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the WIAS_TRACE macro be used instead.The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file. |
| [WIAS_LWARNING function](..\wiamdef\nf-wiamdef-wias_lwarning.md) | The WIAS_LWARNING macro is obsolete for Windows Vista and later.The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file. |
| [WIAS_TRACE function](..\wiamdef\nf-wiamdef-wias_trace.md) | The WIAS_TRACE macro writes a diagnostic message to the Wiatrace.log file. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [AddItemToFolder method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-additemtofolder.md) | The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree. |
| [DetectRegions method](..\wia_lh\nf-wia_lh-iwiasegmentationfilter-detectregions.md) | The IWiaSegmentationFilter |
| [DumpItemData method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-dumpitemdata.md) | The IWiaDrvItem |
| [FilterPreviewImage method](..\wia_lh\nf-wia_lh-iwiaimagefilter-filterpreviewimage.md) | The IWiaImageFilter |
| [FindChildItemByName method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-findchilditembyname.md) | The IWiaDrvItem |
| [FindItemByName method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-finditembyname.md) | The IWiaDrvItem |
| [GetDeviceSpecContext method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getdevicespeccontext.md) | The IWiaDrvItem |
| [GetFirstChildItem method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getfirstchilditem.md) | The IWiaDrvItem |
| [GetFullItemName method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getfullitemname.md) | The IWiaDrvItem |
| [GetItemFlags method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getitemflags.md) | The IWiaDrvItem |
| [GetItemName method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getitemname.md) | The IWiaDrvItem |
| [GetNextSiblingItem method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem.md) | The IWiaDrvItem |
| [GetNextStream method](..\wia_lh\nf-wia_lh-iwiatransfercallback-getnextstream.md) | The IWiaTransferCallback |
| [GetNextStream method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrvtransfercallback-getnextstream.md) | Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload). |
| [GetParentItem method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-getparentitem.md) | The IWiaDrvItem |
| [GetStatusDescription method](..\wia_lh\nf-wia_lh-iwiaerrorhandler-getstatusdescription.md) | The system UI calls the GetStatusDescription method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension. |
| [InitializeFilter method](..\wia_lh\nf-wia_lh-iwiaimagefilter-initializefilter.md) | The IWiaImageFilter |
| [InitializeLog method](..\wia_lh\nf-wia_lh-iwialog-initializelog.md) | Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.The IWiaLog |
| [Log method](..\wia_lh\nf-wia_lh-iwialog-log.md) | The IWiaLog interface is obsolete for Windows XP and later, and is no longer supported. Use the Diagnostic Log Macros instead.The IWiaLog |
| [MiniDrvCallback method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback.md) | The MiniDrvCallback method provides a callback method for WIA minidrivers to use during a callback data transfer. |
| [RemoveItemFromFolder method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-removeitemfromfolder.md) | The IWiaDrvItem |
| [ReportStatus method](..\wia_lh\nf-wia_lh-iwiaerrorhandler-reportstatus.md) | The ReportStatus method displays information about an error or status during a transfer. In some cases this method allows the user to recover from an error. |
| [SendMessage method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrvtransfercallback-sendmessage.md) | Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer. |
| [TransferCallback method](..\wia_lh\nf-wia_lh-iwiatransfercallback-transfercallback.md) | The IWiaTransferCallback |
| [UnlinkItemTree method](..\wiamindr_lh\nf-wiamindr_lh-iwiadrvitem-unlinkitemtree.md) | The IWiaDrvItem |
| [drvAcquireItemData method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata.md) | The IWiaMiniDrv |
| [drvAnalyzeItem method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem.md) | The IWiaMiniDrv |
| [drvDeleteItem method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvdeleteitem.md) | The IWiaMiniDrv |
| [drvDeviceCommand method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvdevicecommand.md) | The IWiaMiniDrv |
| [drvFreeDrvItemContext method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvfreedrvitemcontext.md) | The IWiaMiniDrv |
| [drvGetCapabilities method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities.md) | The IWiaMiniDrv |
| [drvGetDeviceErrorStr method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md) | The IWiaMiniDrv |
| [drvGetWiaFormatInfo method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvgetwiaformatinfo.md) | The IWiaMiniDrv |
| [drvInitItemProperties method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvinititemproperties.md) | The IWiaMiniDrv |
| [drvInitializeWia method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvinitializewia.md) | The IWiaMiniDrv |
| [drvLockWiaDevice method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvlockwiadevice.md) | The IWiaMiniDrv |
| [drvNotifyPnpEvent method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvnotifypnpevent.md) | The IWiaMiniDrv |
| [drvReadItemProperties method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties.md) | The IWiaMiniDrv |
| [drvUnInitializeWia method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvuninitializewia.md) | The IWiaMiniDrv |
| [drvUnLockWiaDevice method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvunlockwiadevice.md) | The IWiaMiniDrv |
| [drvValidateItemProperties method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties.md) | The IWiaMiniDrv |
| [drvWriteItemProperties method](..\wiamindr_lh\nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties.md) | The IWiaMiniDrv |
| [hResult method](..\wia_lh\nf-wia_lh-iwialog-hresult.md) | Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported. |
