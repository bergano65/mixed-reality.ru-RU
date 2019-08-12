---
title: Устранение неполадок и ограничения удаленного взаимодействия с holographic
description: Действия по устранению неполадок для удаленного взаимодействия holographic в HoloLens 2.
author: FlorianBagarMicrosoft
ms.author: flbagar
ms.date: 08/01/2019
ms.topic: article
keywords: Windows Mixed Reality, голограммы, holographic удаленное взаимодействие, удаленная визуализация, Сетевая визуализация, HoloLens, удаленные голограммы, устранение неполадок, помощь
ms.openlocfilehash: 86b6979dbfc9b514b3af13ebdcc3d3ece17e6335
ms.sourcegitcommit: ca949efe0279995a376750d89e23d7123eb44846
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2019
ms.locfileid: "68718148"
---
# <a name="holographic-remoting-troubleshooting"></a><span data-ttu-id="d0979-104">Устранение неполадок удаленного взаимодействия с holographic</span><span class="sxs-lookup"><span data-stu-id="d0979-104">Holographic Remoting troubleshooting</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0979-105">Это руководство относится к удаленному взаимодействию с HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d0979-105">This guidance is specific to Holographic Remoting on HoloLens 2.</span></span>

## <a name="spectre-mitigated-libraries-not-found"></a><span data-ttu-id="d0979-106">Не найдены библиотеки, снижающие опасность устранением рисков Spectre.</span><span class="sxs-lookup"><span data-stu-id="d0979-106">Spectre mitigated libraries not found.</span></span>

<span data-ttu-id="d0979-107">В примере приложений с удаленным взаимодействием с устранением рисков Spectre (/Qspectre) включено устранение рисков в конфигурации выпуска.</span><span class="sxs-lookup"><span data-stu-id="d0979-107">Holographic Remoting sample apps have Spectre mitigation (/Qspectre) enabled in Release configuration.</span></span>

<span data-ttu-id="d0979-108">Если вы получаете неустранимую ошибку компоновщика, в которой говорится, что не удается открыть "vccorlib. lib", убедитесь, что Рабочая нагрузка Visual Studio включает библиотеки, снижающие опасность устранением рисков Spectre.</span><span class="sxs-lookup"><span data-stu-id="d0979-108">If you get a fatal linker error which states that 'vccorlib.lib' cannot be opened, make sure that your Visual Studio Workload includes the Spectre mitigated libraries.</span></span> <span data-ttu-id="d0979-109">Дополнительные сведения см. в разделе https://aka.ms/Ofhn4c.</span><span class="sxs-lookup"><span data-stu-id="d0979-109">See https://aka.ms/Ofhn4c for more information.</span></span>

# <a name="limitations"></a><span data-ttu-id="d0979-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d0979-110">Limitations</span></span>

<span data-ttu-id="d0979-111">В настоящее время следующие API **не** поддерживаются при использовании удаленного взаимодействия holographic для HoloLens 2 и вызывают ```ERROR_NOT_SUPPORTED``` ошибку, если не указано иное:</span><span class="sxs-lookup"><span data-stu-id="d0979-111">The following APIs are currently **not** supported when using Holographic Remoting for HoloLens 2 and will raises an ```ERROR_NOT_SUPPORTED``` error unless otherwise stated:</span></span>

[<span data-ttu-id="d0979-112">Windows.Graphics.Holographic</span><span class="sxs-lookup"><span data-stu-id="d0979-112">Windows.Graphics.Holographic</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic)

* [<span data-ttu-id="d0979-113">Холографиккамера. Виевконфигуратион</span><span class="sxs-lookup"><span data-stu-id="d0979-113">HolographicCamera.ViewConfiguration</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographiccamera.viewconfiguration)
* [<span data-ttu-id="d0979-114">Холографиккамерапосе. Оверридепрожектионтрансформ</span><span class="sxs-lookup"><span data-stu-id="d0979-114">HolographicCameraPose.OverrideProjectionTransform</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographiccamerapose.overrideprojectiontransform)
* [<span data-ttu-id="d0979-115">Холографиккамерапосе. Оверридевиевпорт</span><span class="sxs-lookup"><span data-stu-id="d0979-115">HolographicCameraPose.OverrideViewport</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographiccamerapose.overrideviewport)
* [<span data-ttu-id="d0979-116">Холографиккамерапосе. Оверридевиевтрансформ</span><span class="sxs-lookup"><span data-stu-id="d0979-116">HolographicCameraPose.OverrideViewTransform</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographiccamerapose.overrideviewtransform)
* <span data-ttu-id="d0979-117">[Холографиккамерарендерингпараметерс. CommitDirect3D11DepthBuffer](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographiccamerarenderingparameters.commitdirect3d11depthbuffer#Windows_Graphics_Holographic_HolographicCameraRenderingParameters_CommitDirect3D11DepthBuffer_Windows_Graphics_DirectX_Direct3D11_IDirect3DSurface_) — не завершается ошибкой, но буфер глубины не будет удален.</span><span class="sxs-lookup"><span data-stu-id="d0979-117">[HolographicCameraRenderingParameters.CommitDirect3D11DepthBuffer](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographiccamerarenderingparameters.commitdirect3d11depthbuffer#Windows_Graphics_Holographic_HolographicCameraRenderingParameters_CommitDirect3D11DepthBuffer_Windows_Graphics_DirectX_Direct3D11_IDirect3DSurface_) - Does not fail but depth buffer will not be remoted.</span></span>
* [<span data-ttu-id="d0979-118">Холографикдисплай. Трижетвиевконфигуратион</span><span class="sxs-lookup"><span data-stu-id="d0979-118">HolographicDisplay.TryGetViewConfiguration</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographicdisplay.trygetviewconfiguration)
* [<span data-ttu-id="d0979-119">Холографикспаце. Креатефрамепресентатионмонитор</span><span class="sxs-lookup"><span data-stu-id="d0979-119">HolographicSpace.CreateFramePresentationMonitor</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.graphics.holographic.holographicspace.createframepresentationmonitor)

[<span data-ttu-id="d0979-120">Windows.Perception.Spatial</span><span class="sxs-lookup"><span data-stu-id="d0979-120">Windows.Perception.Spatial</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial)

* [<span data-ttu-id="d0979-121">SpatialLocation. Абсолутеангуларакцелератион</span><span class="sxs-lookup"><span data-stu-id="d0979-121">SpatialLocation.AbsoluteAngularAcceleration</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatiallocation.absoluteangularacceleration)
* [<span data-ttu-id="d0979-122">SpatialLocation. Абсолутеангуларакцелератионаксисангле</span><span class="sxs-lookup"><span data-stu-id="d0979-122">SpatialLocation.AbsoluteAngularAccelerationAxisAngle</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatiallocation.absoluteangularaccelerationaxisangle)
* [<span data-ttu-id="d0979-123">SpatialLocation. АбсолутеангуларвелоЦити</span><span class="sxs-lookup"><span data-stu-id="d0979-123">SpatialLocation.AbsoluteAngularVelocity</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatiallocation.absoluteangularvelocity)
* [<span data-ttu-id="d0979-124">SpatialLocation. АбсолутеангуларвелоЦитяксисангле</span><span class="sxs-lookup"><span data-stu-id="d0979-124">SpatialLocation.AbsoluteAngularVelocityAxisAngle</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatiallocation.absoluteangularvelocityaxisangle)
* [<span data-ttu-id="d0979-125">SpatialLocation. Абсолутелинеаракцелератион</span><span class="sxs-lookup"><span data-stu-id="d0979-125">SpatialLocation.AbsoluteLinearAcceleration</span></span>](https://docs.microsoft.com/is-is/uwp/api/windows.perception.spatial.spatiallocation.absolutelinearacceleration)
* [<span data-ttu-id="d0979-126">SpatialLocation. АбсолутелинеарвелоЦити</span><span class="sxs-lookup"><span data-stu-id="d0979-126">SpatialLocation.AbsoluteLinearVelocity</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatiallocation.absolutelinearvelocity)
* <span data-ttu-id="d0979-127">[Спатиалстажефрамеофреференце. Current](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialstageframeofreference.current) — всегда возвращает ```nullptr```значение.</span><span class="sxs-lookup"><span data-stu-id="d0979-127">[SpatialStageFrameOfReference.Current](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialstageframeofreference.current) - Always returns ```nullptr```.</span></span>
* [<span data-ttu-id="d0979-128">Спатиалстажефрамеофреференце. Рекуестневстажеасинк</span><span class="sxs-lookup"><span data-stu-id="d0979-128">SpatialStageFrameOfReference.RequestNewStageAsync</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialstageframeofreference.requestnewstageasync)
* [<span data-ttu-id="d0979-129">Спатиаланчор. Ремоведбюсер</span><span class="sxs-lookup"><span data-stu-id="d0979-129">SpatialAnchor.RemovedByUser</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchor.removedbyuser)
* <span data-ttu-id="d0979-130">[Спатиаланчорекспортер. по умолчанию](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchorexporter.getdefault
) — всегда возвращает. ```nullptr```</span><span class="sxs-lookup"><span data-stu-id="d0979-130">[SpatialAnchorExporter.GetDefault](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchorexporter.getdefault
) - Always returns ```nullptr```.</span></span>
* <span data-ttu-id="d0979-131">[Спатиаланчорекспортер. рекуестакцессасинк](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchorexporter.requestaccessasync
) — асинхронная операция всегда завершается ```SpatialPerceptionAccessStatus.DeniedBySystem```с.</span><span class="sxs-lookup"><span data-stu-id="d0979-131">[SpatialAnchorExporter.RequestAccessAsync](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchorexporter.requestaccessasync
) - Async operation always completes with ```SpatialPerceptionAccessStatus.DeniedBySystem```.</span></span>
* <span data-ttu-id="d0979-132">[Спатиаланчортрансферманажер. рекуестакцессасинк](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchortransfermanager.requestaccessasync#Windows_Perception_Spatial_SpatialAnchorTransferManager_RequestAccessAsync) — асинхронная операция всегда завершается ```SpatialPerceptionAccessStatus.DeniedBySystem```с.</span><span class="sxs-lookup"><span data-stu-id="d0979-132">[SpatialAnchorTransferManager.RequestAccessAsync](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchortransfermanager.requestaccessasync#Windows_Perception_Spatial_SpatialAnchorTransferManager_RequestAccessAsync) - Async operation always completes with ```SpatialPerceptionAccessStatus.DeniedBySystem```.</span></span>
* <span data-ttu-id="d0979-133">[Спатиаланчортрансферманажер. трекспортанчорсасинк](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchortransfermanager.tryexportanchorsasync#Windows_Perception_Spatial_SpatialAnchorTransferManager_TryExportAnchorsAsync_Windows_Foundation_Collections_IIterable_Windows_Foundation_Collections_IKeyValuePair_System_String_Windows_Perception_Spatial_SpatialAnchor___Windows_Storage_Streams_IOutputStream_) — асинхронная операция всегда завершается ```false```с.</span><span class="sxs-lookup"><span data-stu-id="d0979-133">[SpatialAnchorTransferManager.TryExportAnchorsAsync](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchortransfermanager.tryexportanchorsasync#Windows_Perception_Spatial_SpatialAnchorTransferManager_TryExportAnchorsAsync_Windows_Foundation_Collections_IIterable_Windows_Foundation_Collections_IKeyValuePair_System_String_Windows_Perception_Spatial_SpatialAnchor___Windows_Storage_Streams_IOutputStream_) - Async operation always completes with ```false```.</span></span>
* <span data-ttu-id="d0979-134">[Спатиаланчортрансферманажер. тримпортанчорсасинк](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchortransfermanager.tryimportanchorsasync
) — асинхронная операция всегда завершается ```nullptr```с.</span><span class="sxs-lookup"><span data-stu-id="d0979-134">[SpatialAnchorTransferManager.TryImportAnchorsAsync](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.spatialanchortransfermanager.tryimportanchorsasync
) - Async operation always completes with ```nullptr```.</span></span>

[<span data-ttu-id="d0979-135">Windows.UI.Input.Spatial</span><span class="sxs-lookup"><span data-stu-id="d0979-135">Windows.UI.Input.Spatial</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial)

* [<span data-ttu-id="d0979-136">Спатиалинтерактионсаурце. Трикреатехандмешобсервер</span><span class="sxs-lookup"><span data-stu-id="d0979-136">SpatialInteractionSource.TryCreateHandMeshObserver</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsource.trycreatehandmeshobserver#Windows_UI_Input_Spatial_SpatialInteractionSource_TryCreateHandMeshObserver)
* [<span data-ttu-id="d0979-137">Спатиалинтерактионсаурце. Трикреатехандмешобсерверасинк</span><span class="sxs-lookup"><span data-stu-id="d0979-137">SpatialInteractionSource.TryCreateHandMeshObserverAsync</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsource.trycreatehandmeshobserverasync)

[<span data-ttu-id="d0979-138">Windows.Perception.Spatial.Preview</span><span class="sxs-lookup"><span data-stu-id="d0979-138">Windows.Perception.Spatial.Preview</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.preview)

* [<span data-ttu-id="d0979-139">Спатиалграфинтероппревиев. Креателокаторфорноде</span><span class="sxs-lookup"><span data-stu-id="d0979-139">SpatialGraphInteropPreview.CreateLocatorForNode</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.preview.spatialgraphinteroppreview.createlocatorfornode)
* [<span data-ttu-id="d0979-140">Спатиалграфинтероппревиев. Трикреатефрамеофреференце</span><span class="sxs-lookup"><span data-stu-id="d0979-140">SpatialGraphInteropPreview.TryCreateFrameOfReference</span></span>](https://docs.microsoft.com/en-us/uwp/api/windows.perception.spatial.preview.spatialgraphinteroppreview.trycreateframeofreference)

## <a name="see-also"></a><span data-ttu-id="d0979-141">См. также</span><span class="sxs-lookup"><span data-stu-id="d0979-141">See Also</span></span>
* [<span data-ttu-id="d0979-142">Создание хост-приложения holographic с удаленным взаимодействием</span><span class="sxs-lookup"><span data-stu-id="d0979-142">Writing a Holographic Remoting host app</span></span>](holographic-remoting-create-host.md)
* [<span data-ttu-id="d0979-143">Написание пользовательского приложения для удаленного взаимодействия holographic</span><span class="sxs-lookup"><span data-stu-id="d0979-143">Writing a custom Holographic Remoting player app</span></span>](holographic-remoting-create-player.md)
* [<span data-ttu-id="d0979-144">Условия лицензии на программное обеспечение удаленного взаимодействия holographic</span><span class="sxs-lookup"><span data-stu-id="d0979-144">Holographic Remoting software license terms</span></span>](https://docs.microsoft.com/en-us/legal/mixed-reality/microsoft-holographic-remoting-software-license-terms)
* [<span data-ttu-id="d0979-145">Заявление о конфиденциальности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d0979-145">Microsoft Privacy Statement</span></span>](https://go.microsoft.com/fwlink/?LinkId=521839)