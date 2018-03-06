---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEODEVICEFUNCS
title: D3DWDDM2_0DDI_VIDEODEVICEFUNCS
author: windows-driver-content
description: Specifies the video function table for the Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.0 and later drivers.
old-location: display\d3dwddm2_0ddi_videodevicefuncs.htm
old-project: display
ms.assetid: 59D06B73-413B-4595-841E-7E0A696A3AC2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DWDDM2_0DDI_VIDEODEVICEFUNCS, D3DWDDM2_0DDI_VIDEODEVICEFUNCS structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEODEVICEFUNCS, display.d3dwddm2_0ddi_videodevicefuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_VIDEODEVICEFUNCS
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEODEVICEFUNCS
---

# D3DWDDM2_0DDI_VIDEODEVICEFUNCS structure
Specifies the video function table for the  Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.0 and later drivers.

## Syntax
````
typedef struct D3DWDDM2_0DDI_VIDEODEVICEFUNCS {
  PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT                  pfnGetVideoDecoderProfileCount;
  PFND3D11_1DDI_GETVIDEODECODERPROFILE                       pfnGetVideoDecoderProfile;
  PFND3D11_1DDI_CHECKVIDEODECODERFORMAT                      pfnCheckVideoDecoderFormat;
  PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT                   pfnGetVideoDecoderConfigCount;
  PFND3D11_1DDI_GETVIDEODECODERCONFIG                        pfnGetVideoDecoderConfig;
  PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT               pfnGetVideoDecoderBufferTypeCount;
  PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO                    pfnGetVideoDecoderBufferInfo;
  PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE                  pfnCalcPrivateVideoDecoderSize;
  PFND3D11_1DDI_CREATEVIDEODECODER                           pfnCreateVideoDecoder;
  PFND3D11_1DDI_DESTROYVIDEODECODER                          pfnDestroyVideoDecoder;
  PFND3D11_1DDI_VIDEODECODEREXTENSION                        pfnVideoDecoderExtension;
  PFND3D11_1DDI_VIDEODECODERBEGINFRAME                       pfnVideoDecoderBeginFrame;
  PFND3D11_1DDI_VIDEODECODERENDFRAME                         pfnVideoDecoderEndFrame;
  PFND3D11_1DDI_VIDEODECODERSUBMITBUFFERS                    pfnVideoDecoderSubmitBuffers;
  PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE            pfnCalcPrivateVideoProcessorEnumSize;
  PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM                     pfnCreateVideoProcessorEnum;
  PFND3D11_1DDI_DESTROYVIDEOPROCESSORENUM                    pfnDestroyVideoProcessorEnum;
  PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT                    pfnCheckVideoProcessorFormat;
  PFND3D11_1DDI_GETVIDEOPROCESSORCAPS                        pfnGetVideoProcessorCaps;
  PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS          pfnGetVideoProcessorRateConversionCaps;
  PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE                  pfnGetVideoProcessorCustomRate;
  PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE                 pfnGetVideoProcessorFilterRange;
  PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE                pfnCalcPrivateVideoProcessorSize;
  PFND3D11_1DDI_CREATEVIDEOPROCESSOR                         pfnCreateVideoProcessor;
  PFND3D11_1DDI_DESTROYVIDEOPROCESSOR                        pfnDestroyVideoProcessor;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT            pfnVideoProcessorSetOutputTargetRect;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR       pfnVideoProcessorSetOutputBackgroundColor;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE            pfnVideoProcessorSetOutputColorSpace;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE         pfnVideoProcessorSetOutputAlphaFillMode;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION          pfnVideoProcessorSetOutputConstriction;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE            pfnVideoProcessorSetOutputStereoMode;
  PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION             pfnVideoProcessorSetOutputExtension;
  PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION             pfnVideoProcessorGetOutputExtension;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT           pfnVideoProcessorSetStreamFrameFormat;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE            pfnVideoProcessorSetStreamColorSpace;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE            pfnVideoProcessorSetStreamOutputRate;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT            pfnVideoProcessorSetStreamSourceRect;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT              pfnVideoProcessorSetStreamDestRect;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA                 pfnVideoProcessorSetStreamAlpha;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE               pfnVideoProcessorSetStreamPalette;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO      pfnVideoProcessorSetStreamPixelAspectRatio;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY               pfnVideoProcessorSetStreamLumaKey;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT          pfnVideoProcessorSetStreamStereoFormat;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE    pfnVideoProcessorSetStreamAutoProcessingMode;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER                pfnVideoProcessorSetStreamFilter;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION             pfnVideoProcessorSetStreamExtension;
  PFND3D11_1DDI_VIDEOPROCESSORGETSTREAMEXTENSION             pfnVideoProcessorGetStreamExtension;
  PFND3D11_1DDI_VIDEOPROCESSORBLT                            pfnVideoProcessorBlt;
  PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE        pfnCalcPrivateVideoDecoderOutputViewSize;
  PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW                 pfnCreateVideoDecoderOutputView;
  PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW                pfnDestroyVideoDecoderOutputView;
  PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE       pfnCalcPrivateVideoProcessorInputViewSize;
  PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW                pfnCreateVideoProcessorInputView;
  PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW               pfnDestroyVideoProcessorInputView;
  PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSOROUTPUTVIEWSIZE      pfnCalcPrivateVideoProcessorOutputViewSize;
  PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW               pfnCreateVideoProcessorOutputView;
  PFND3D11_1DDI_DESTROYVIDEOPROCESSOROUTPUTVIEW              pfnDestroyVideoProcessorOutputView;
  PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD  pfnVideoProcessorInputViewReadAfterWriteHazard;
  PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS                     pfnGetContentProtectionCaps;
  PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE                     pfnGetCryptoKeyExchangeType;
  PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE                 pfnCalcPrivateCryptoSessionSize;
  PFND3D11_1DDI_CREATECRYPTOSESSION                          pfnCreateCryptoSession;
  PFND3D11_1DDI_DESTROYCRYPTOSESSION                         pfnDestroyCryptoSession;
  PFND3D11_1DDI_GETCERTIFICATESIZE                           pfnGetCertificateSize;
  PFND3D11_1DDI_GETCERTIFICATE                               pfnGetCertificate;
  PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE            pfnNegotiateCryptoSessionKeyExchange;
  PFND3D11_1DDI_ENCRYPTIONBLT                                pfnEncryptionBlt;
  PFND3D11_1DDI_DECRYPTIONBLT                                pfnDecryptionBlt;
  PFND3D11_1DDI_STARTSESSIONKEYREFRESH                       pfnStartSessionKeyRefresh;
  PFND3D11_1DDI_FINISHSESSIONKEYREFRESH                      pfnFinishSessionKeyRefresh;
  PFND3D11_1DDI_GETENCRYPTIONBLTKEY                          pfnGetEncryptionBltKey;
  PFND3D11_1DDI_CALCPRIVATEAUTHENTICATEDCHANNELSIZE          pfnCalcPrivateAuthenticatedChannelSize;
  PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL                   pfnCreateAuthenticatedChannel;
  PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL                  pfnDestroyAuthenticatedChannel;
  PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE     pfnNegotiateAuthenticatedChannelKeyExchange;
  PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL                    pfnQueryAuthenticatedChannel;
  PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL                pfnConfigureAuthenticatedChannel;
  PFND3D11_1DDI_VIDEODECODERGETHANDLE                        pfnVideoDecoderGetHandle;
  PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE                       pfnCryptoSessionGetHandle;
  PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMROTATION              pfnVideoProcessorSetStreamRotation;
  PFND3D11_1DDI_GETCAPTUREHANDLE                             pfnGetCaptureHandle;
  PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY                  pfnGetDataForNewHardwareKey;
  PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS                  pfnCheckCryptoSessionStatus;
  PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1                pfnVideoDecoderSubmitBuffers1;
  PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES                    pfnQueryVideoCapabilities;
  PFND3DWDDM2_0DDI_CHECKVIDEOPROCESSORFORMATCONVERSION       pfnCheckVideoProcessorFormatConversion;
  PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING            pfnVideoDecoderEnableDownsampling;
  PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING            pfnVideoDecoderUpdateDownsampling;
  PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR             pfnVideoProcessorSetStreamMirror;
  PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE1        pfnVideoProcessorSetOutputColorSpace1;
  PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1        pfnVideoProcessorSetStreamColorSpace1;
  PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE        pfnVideoProcessorSetOutputShaderUsage;
  PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS            pfnVideoProcessorGetBehaviorHints;
  PFND3DWDDM2_0DDI_GETCRYPTOSESSIONPRIVATEDATASIZE           pfnGetCryptoSessionPrivateDataSize        ;
} D3DWDDM2_0DDI_VIDEODEVICEFUNCS;
````

## Members


`pfnCalcPrivateAuthenticatedChannelSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateauthenticatedchannelsize.md">CalcPrivateAuthenticatedChannelSize</a> function.

`pfnCalcPrivateCryptoSessionSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize.md">CalcPrivateCryptoSessionSize</a> function.

`pfnCalcPrivateVideoDecoderOutputViewSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecoderoutputviewsize.md">CalcPrivateVideoDecoderOutputViewSize</a> function.

`pfnCalcPrivateVideoDecoderSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md">CalcPrivateVideoDecoderSize</a> function.

`pfnCalcPrivateVideoProcessorEnumSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorenumsize.md">CalcPrivateVideoProcessorEnumSize</a> function.

`pfnCalcPrivateVideoProcessorInputViewSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorinputviewsize.md">CalcPrivateVideoProcessorInputViewSize</a> function.

`pfnCalcPrivateVideoProcessorOutputViewSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a> function.

`pfnCalcPrivateVideoProcessorSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize.md">CalcPrivateVideoProcessorSize</a> function.

`pfnCheckCryptoSessionStatus`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_checkcryptosessionstatus.md">CheckCryptoSessionStatus</a> function.

`pfnCheckVideoDecoderFormat`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkvideodecoderformat.md">CheckVideoDecoderFormat</a> function.

`pfnCheckVideoProcessorFormat`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkvideoprocessorformat.md">CheckVideoProcessorFormat</a> function.

`pfnCheckVideoProcessorFormatConversion`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion.md">CheckVideoProcessorFormatConversion</a> function.

`pfnConfigureAuthenticatedChannel`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.

`pfnCreateAuthenticatedChannel`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.

`pfnCreateCryptoSession`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.

`pfnCreateVideoDecoder`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a> function.

`pfnCreateVideoDecoderOutputView`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a> function.

`pfnCreateVideoProcessor`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function.

`pfnCreateVideoProcessorEnum`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a> function.

`pfnCreateVideoProcessorInputView`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a> function.

`pfnCreateVideoProcessorOutputView`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessoroutputview.md">CreateVideoProcessorOutputView</a> function.

`pfnCryptoSessionGetHandle`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_cryptosessiongethandle.md">CryptoSessionGetHandle</a> function.

`pfnDecryptionBlt`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt.md">DecryptionBlt(D3D11_1)</a> function.

`pfnDestroyAuthenticatedChannel`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a> function.

`pfnDestroyCryptoSession`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroycryptosession.md">DestroyCryptoSession</a> function.

`pfnDestroyVideoDecoder`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoder.md">DestroyVideoDecoder</a> function.

`pfnDestroyVideoDecoderOutputView`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoderoutputview.md">DestroyVideoDecoderOutputView</a> function.

`pfnDestroyVideoProcessor`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessor.md">DestroyVideoProcessor</a> function.

`pfnDestroyVideoProcessorEnum`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorenum.md">DestroyVideoProcessorEnum</a> function.

`pfnDestroyVideoProcessorInputView`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorinputview.md">DestroyVideoProcessorInputView</a> function.

`pfnDestroyVideoProcessorOutputView`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessoroutputview.md">DestroyVideoProcessorOutputView</a> function.

`pfnEncryptionBlt`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a> function.

`pfnFinishSessionKeyRefresh`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function.

`pfnGetCaptureHandle`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a> function.

`pfnGetCertificate`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a> function.

`pfnGetCertificateSize`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a> function.

`pfnGetContentProtectionCaps`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcontentprotectioncaps.md">GetContentProtectionCaps</a> function.

`pfnGetCryptoKeyExchangeType`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype.md">GetCryptoKeyExchangeType</a> function.

`pfnGetCryptoSessionPrivateDataSize`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md">GetCryptoSessionPrivateDataSize</a> function.

`pfnGetDataForNewHardwareKey`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getdatafornewhardwarekey.md">GetDataForNewHardwareKey</a> function.

`pfnGetEncryptionBltKey`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey.md">GetEncryptionBltKey</a> function.

`pfnGetVideoDecoderBufferInfo`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbufferinfo.md">GetVideoDecoderBufferInfo</a> function.

`pfnGetVideoDecoderBufferTypeCount`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbuffertypecount.md">GetVideoDecoderBufferTypeCount</a> function.

`pfnGetVideoDecoderConfig`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfig.md">GetVideoDecoderConfig</a> function.

`pfnGetVideoDecoderConfigCount`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount.md">GetVideoDecoderConfig</a> function.

`pfnGetVideoDecoderProfile`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofile.md">VideoDecoderProfile</a> function.

`pfnGetVideoDecoderProfileCount`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount.md">VideoDecoderProfileCount</a> function.

`pfnGetVideoProcessorCaps`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function.

`pfnGetVideoProcessorCustomRate`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md">GetVideoProcessorCustomRate</a> function.

`pfnGetVideoProcessorFilterRange`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorfilterrange.md">GetVideoProcessorFilterRange</a> function.

`pfnGetVideoProcessorRateConversionCaps`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a> function.

`pfnNegotiateAuthenticatedChannelKeyExchange`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiateauthenticatedchannelkeyexchange.md">NegotiateAuthenticatedChannelKeyExchange</a> function.

`pfnNegotiateCryptoSessionKeyExchange`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a> function.

`pfnQueryAuthenticatedChannel`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> function.

`pfnQueryVideoCapabilities`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md">QueryVideoCapabilities</a> function.

`pfnStartSessionKeyRefresh`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a> function.

`pfnVideoDecoderBeginFrame`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a> function.

`pfnVideoDecoderEnableDownsampling`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling.md">VideoDecoderEnableDownsampling</a> function.

`pfnVideoDecoderEndFrame`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderendframe.md">VideoDecoderEndFrame</a> function.

`pfnVideoDecoderExtension`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderextension.md">VideoDecoderExtension</a> function.

`pfnVideoDecoderGetHandle`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecodergethandle.md">VideoDecoderGetHandle</a> function.

`pfnVideoDecoderSubmitBuffers`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers.md">VideoDecoderSubmitBuffers</a> function.

`pfnVideoDecoderSubmitBuffers1`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecodersubmitbuffers1.md">VideoDecoderSubmitBuffers1</a> function.

`pfnVideoDecoderUpdateDownsampling`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderupdatedownsampling.md">VideoDecoderUpdateDownsampling</a> function.

`pfnVideoProcessorBlt`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a> function.

`pfnVideoProcessorGetBehaviorHints`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorgetbehaviorhints.md">VideoProcessorGetBehaviorHints</a> function.

`pfnVideoProcessorGetOutputExtension`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetoutputextension.md">VideoProcessorGetOutputExtension</a> function.

`pfnVideoProcessorGetStreamExtension`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetstreamextension.md">VideoProcessorGetStreamExtension</a> function.

`pfnVideoProcessorInputViewReadAfterWriteHazard`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorinputviewreadafterwritehazard.md">VideoProcessorInputViewReadAfterWriteHazard</a> function.

`pfnVideoProcessorSetOutputAlphaFillMode`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a> function.

`pfnVideoProcessorSetOutputBackgroundColor`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor.md">VideoProcessorSetOutputBackgroundColor</a> function.

`pfnVideoProcessorSetOutputColorSpace`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputcolorspace.md">VideoProcessorSetOutputColorSpace</a> function.

`pfnVideoProcessorSetOutputColorSpace1`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputcolorspace1.md">VideoProcessorSetOutputColorSpace1</a> function.

`pfnVideoProcessorSetOutputConstriction`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md">VideoProcessorSetOutputConstriction</a> function.

`pfnVideoProcessorSetOutputExtension`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputextension.md">VideoProcessorSetOutputExtension</a> function.

`pfnVideoProcessorSetOutputShaderUsage`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputshaderusage.md">VideoProcessorSetOutputShaderUsage</a> function.

`pfnVideoProcessorSetOutputStereoMode`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode.md">VideoProcessorSetOutputStereoMode</a> function.

`pfnVideoProcessorSetOutputTargetRect`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputtargetrect.md">VideoProcessorSetOutputTargetRect</a> function.

`pfnVideoProcessorSetStreamAlpha`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamalpha.md">VideoProcessorSetStreamAlpha</a> function.

`pfnVideoProcessorSetStreamAutoProcessingMode`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamautoprocessingmode.md">VideoProcessorSetStreamAutoProcessingMode</a> function.

`pfnVideoProcessorSetStreamColorSpace`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamcolorspace.md">VideoProcessorSetStreamColorSpace</a> function.

`pfnVideoProcessorSetStreamColorSpace1`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreamcolorspace1.md">VideoProcessorSetStreamColorSpace1</a> function.

`pfnVideoProcessorSetStreamDestRect`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamdestrect.md">VideoProcessorSetStreamDestRect</a> function.

`pfnVideoProcessorSetStreamExtension`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamextension.md">VideoProcessorSetStreamExtension</a> function.

`pfnVideoProcessorSetStreamFilter`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamfilter.md">VideoProcessorSetStreamFilter</a> function.

`pfnVideoProcessorSetStreamFrameFormat`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamframeformat.md">VideoProcessorSetStreamFrameFormat</a> function.

`pfnVideoProcessorSetStreamLumaKey`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md">VideoProcessorSetStreamLumaKey</a> function.

`pfnVideoProcessorSetStreamMirror`

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md">VideoProcessorSetStreamMirror</a> function.

`pfnVideoProcessorSetStreamOutputRate`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamoutputrate.md">VideoProcessorSetStreamOutputRate</a> function.

`pfnVideoProcessorSetStreamPalette`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampalette.md">VideoProcessorSetStreamPalette</a> function.

`pfnVideoProcessorSetStreamPixelAspectRatio`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampixelaspectratio.md">VideoProcessorSetStreamPixelAspectRatio</a> function.

`pfnVideoProcessorSetStreamRotation`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamrotation.md">VideoProcessorSetStreamRotation</a> function.

`pfnVideoProcessorSetStreamSourceRect`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamsourcerect.md">VideoProcessorSetStreamSourceRect</a> function.

`pfnVideoProcessorSetStreamStereoFormat`

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |