---
title: Руководства по портированию приложений
description: Пошаговое валсраугх объясняет, как перенести существующее иммерсивное приложение на Windows Mixed Reality.
author: ChimeraScorn
ms.author: alexturn
ms.date: 10/02/2018
ms.topic: article
keywords: порт, перенос, Unity, по промежуточного слоя, ядро, UWP
ms.openlocfilehash: 5d3debc9a810873f21a9f55a32061565d4ce75ae
ms.sourcegitcommit: 83698638b93c5ba77b3ffc399f1706482539f27b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74539510"
---
# <a name="porting-guides"></a>Руководства по портированию приложений

Windows 10 включает поддержку для повпечатляющих и holographic головных телефонов напрямую. Если вы создали содержимое для другого устройства, например Окулус Рифт или HTC Naopak, они имеют зависимости от библиотек, которые существуют над API платформы операционной системы. Внедрение существующего содержимого в Windows Mixed Reality предполагает изменение целевой платформы на использование этих пакетов SDK для интерфейсов Windows API. [Интерфейсы API платформы Windows для смешанной реальности](https://docs.microsoft.com/uwp/api/Windows.Perception) работают только в модели приложений универсальная платформа Windows (UWP). Если ваше приложение еще не создано для UWP, перенос в UWP будет частью процесса переноса.

## <a name="porting-overview"></a>Общие сведения о переносе

На высоком уровне ниже приведены действия по переносу существующего содержимого.
1. **Убедитесь, что на компьютере работает обновление Windows 10 Creators Update (16299).** Мы больше не рекомендуем получать предварительные сборки от программы предварительной оценки, так как эти сборки не будут самыми стабильными при разработке смешанной реальности.
2. **Обновите версию графического или игрового модуля до последней версии.** Обработчики игр должны поддерживать версию пакета SDK для Windows 10 10.0.15063.0 (выпущена в апреле 2017) или более поздней версии.
3. **Обновите любое промежуточное программное обеспечение, подключаемые модули или компоненты.** Если приложение содержит какие-либо компоненты, рекомендуется выполнить обновление до последней версии. Более новые версии наиболее распространенных подключаемых модулей имеют поддержку UWP.
4. **Удалите зависимости от повторяющихся пакетов SDK**. В зависимости от устройства, для которого предназначено содержимое, необходимо удалить или условно скомпилировать этот пакет SDK (например, Стеамвр), чтобы вместо этого можно было ориентироваться на API Windows.
5. **Работа с проблемами сборки.** На этом этапе упражнение по переносу зависит от вашего приложения, подсистемы и зависимостей компонентов.

## <a name="common-porting-steps"></a>Общие этапы переноса

### <a name="common-step-1-make-sure-you-have-the-right-development-hardware"></a>Общий шаг 1. Убедитесь, что у вас есть правильное оборудование для разработки

На странице [Установка средств](install-the-tools.md#for-immersive-vr-headset-development) перечислены рекомендуемые средства разработки.

### <a name="common-step-2-upgrade-to-the-latest-flight-of-windows-10"></a>Общий шаг 2. обновление до последнего рейса Windows 10

Платформа Windows Mixed Reality по-прежнему находится в активном состоянии разработки и является наиболее эффективной, мы рекомендуем использовать "Быстрый запуск программы предварительной оценки Windows". Чтобы получить доступ к рейсам Windows, необходимо [присоединиться к программе предварительной оценки Windows](https://insider.windows.com/).
1. Установка [обновления Windows 10 для дизайнеров](https://www.microsoft.com/software-download/windows10)
2. [Присоединяйтесь](https://insider.windows.com/) к программе предварительной оценки Windows.
3. Включить [режим разработчика](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development)
4. Перейдите к разделу "быстрые изменения в [программе предварительной оценки Windows](https://blogs.technet.microsoft.com/uktechnet/2016/07/01/joining-insider-preview) " в разделе "Параметры" — > Обновление & безопасности.

### <a name="common-step-3-upgrade-to-the-most-recent-build-of-visual-studio"></a>Общий шаг 3. обновление до последней сборки Visual Studio
* См. раздел [Установка средств на](install-the-tools.md#installation-checklist) странице Visual Studio 2019.

### <a name="common-step-4-be-ready-for-the-store"></a>Общий шаг 4. готовность к хранению
* Используйте [Комплект сертификации приложений Windows](https://developer.microsoft.com/windows/develop/app-certification-kit) (WACK) на ранних этапах и часто.
* Использовать [анализатор переносимости](https://docs.microsoft.com/dotnet/standard/portability-analyzer) ([Загрузка](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer))

### <a name="common-step-5-choose-the-correct-adapter"></a>Общий шаг 5. Выбор подходящего адаптера
* В таких системах, как записные книжки с двумя графическими процессорами, следует [выбрать правильный адаптер](rendering-in-directx.md#hybrid-graphics-pcs-and-mixed-reality-applications). Это относится к приложениям Unity, а также к собственным приложениям DirectX, где ID3D11Device создается явно или неявно (Media Foundation) для своей функциональности.

## <a name="unity-porting-guidance"></a>Руководство по переносу Unity

### <a name="unity-step-1-follow-the-common-porting-steps"></a>Unity шаг 1. Выполните общие действия по переносу

Выполните все общие действия. На шаге #3 выберите рабочую нагрузку **Разработка игр с помощью Unity** . Вы можете отменить выбор дополнительного компонента редактора Unity, так как вы будете устанавливать более новую версию Unity из приведенных ниже инструкций.

### <a name="unity-step-2-upgrade-to-the-latest-public-build-of-unity-with-windows-mr-support"></a>Unity шаг 2. обновление до последней общедоступной сборки Unity с поддержкой Windows MR
1. Скачайте последнюю [рекомендуемую общедоступную сборку Unity](install-the-tools.md) с поддержкой смешанной реальности.
2. Сохраните копию проекта, прежде чем приступить к работе
3. Ознакомьтесь с [документацией](https://docs.unity3d.com/Manual/UpgradeGuides.html) , доступной в Unity при переносе.
4. Следуйте [инструкциям](https://docs.unity3d.com/Manual/APIUpdater.html) на сайте Unity для использования автоматических средств обновления API.
5. Проверьте, есть ли дополнительные изменения, необходимые для запуска проекта, и выполните все оставшиеся ошибки и предупреждения. Примечание. Если по промежуточного слоя от вас зависит, может потребоваться обновить это по по промежуточного слоя, чтобы начать работу (Дополнительные сведения см. на шаге 3 ниже).

### <a name="unity-step-3-upgrade-your-middleware-to-the-latest-versions"></a>Unity шаг 3. обновление по промежуточного слоя до последних версий

При любом обновлении Unity существует хороший шанс, что необходимо обновить один или несколько пакетов по промежуточного слоя, от которых зависит ваша игра или приложение. Кроме того, в последней версии по промежуточного слоя будет увеличена вероятность успеха в оставшейся части процесса переноса. Многие пакеты по промежуточного слоя недавно добавили поддержку универсальная платформа Windows (UWP), а обновление до последних версий позволит вам использовать эту работу.

### <a name="unity-step-4-target-your-application-to-run-on-universal-windows-platform-uwp"></a>Unity шаг 4. Настройка приложения для запуска на универсальная платформа Windows (UWP)

После установки средств необходимо запустить приложение в качестве универсального приложения Windows.
* Выполните [подробное](https://unity3d.com/partners/microsoft/porting-guides) пошаговое руководство, предоставляемое Unity. Обратите внимание, что вы должны остаться в последнем выпуске LTS (любой выпуск 20xx. 4) для Windows MR.
* Для получения дополнительных ресурсов по разработке UWP ознакомьтесь с руководством по [разработке игр для Windows 10](https://docs.microsoft.com/windows/uwp/gaming/e2e).
* Обратите внимание, что Unity продолжит совершенствовать поддержку IL2CPP; IL2CPP делает некоторые порты UWP значительно проще. Если в настоящее время используется серверная часть сценариев .NET, следует рассмотреть возможность преобразования, чтобы использовать серверную часть IL2CPP.

Примечание. Если в приложении есть зависимости от служб для конкретных устройств, например, в соответствии с Steam, необходимо отключить их на этом шаге. Позже можно будет подключить к эквивалентным службам, предоставляемым Windows.

### <a name="unity-step-5-deprecated"></a>Unity шаг 5. (не рекомендуется)

Шаг 5 больше не требуется. Мы оставляем его здесь, чтобы индексирование шагов не оставалось прежним.

### <a name="unity-step-6-get-your-windows-mixed-reality-hardware-set-up"></a>Unity шаг 6. Настройка оборудования Windows Mixed Reality
1. Ознакомьтесь с этапами [настройки иммерсивного головного телефона](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/before-you-start
)
2. Узнайте об [использовании симулятора Windows Mixed Reality](using-the-windows-mixed-reality-simulator.md) и [навигации на домашней странице Windows Mixed Reality](navigating-the-windows-mixed-reality-home.md)

### <a name="unity-step-7-target-your-application-to-run-on-windows-mixed-reality"></a>Unity шаг 7. Настройка приложения для запуска в Windows Mixed Reality
1. Во-первых, необходимо удалить или условно откомпилировать любую другую поддержку библиотеки, относящуюся к конкретному пакету SDK для VR. Эти активы часто изменяют параметры и свойства проекта способами, несовместимыми с другими пакетами SDK для VR, такими как Windows Mixed Reality.
    * Например, если проект ссылается на пакет SDK для Стеамвр, необходимо будет обновить проект, чтобы исключить эти вызовы API Prefabs и скриптов при экспорте для целевого объекта сборки магазина Windows.
    * В ближайшее время ожидается процедура, исключающая другие пакеты SDK для VR.
2. В проекте Unity [нацеливание на пакет SDK для Windows 10](holograms-100.md#target-windows-10-sdk)
3. Для каждой сцены [Настройте камеру](holograms-100.md#chapter-2---setup-the-camera) .

### <a name="unity-step-8-use-the-stage-to-place-content-on-the-floor"></a>Unity шаг 8. использование этапа для размещения содержимого в этаже

Вы можете создавать возможности смешанной реальности во множестве различных [возможностей масштабирования](coordinate-systems.md).

Если вы переносите **интерфейсное масштабирование**, необходимо убедиться, что Unity настроен на **стационарный** тип пространства отслеживания:

```cs
XRDevice.SetTrackingSpaceType(TrackingSpaceType.Stationary);
```

Этот параметр задает мировую систему координат Unity для отслеживания [стационарной рамки ссылки](coordinate-systems.md#spatial-coordinate-systems). В режиме нестационарного отслеживания содержимое, помещенное в редактор непосредственно перед расположением по умолчанию камеры (переадресация — Z), будет отображаться перед пользователем при запуске приложения. Чтобы перецентрировать исходный элемент пользователя, можно вызвать [XR Unity. Метод Инпуттраккинг. recenter](https://docs.unity3d.com/ScriptReference/XR.InputTracking.Recenter.html) .

Если вы проведете переносные **средства или** **возможности масштабирования комнаты**, вы помещаете содержимое относительно пола. Вы указываете на этаж пользователя с помощью **[пространственного этапа](coordinate-systems.md#spatial-coordinate-systems)** , который представляет определенное пользователем происхождение на уровне пола и дополнительную границу комнаты, настраивается во время первого запуска. Для этих возможностей необходимо убедиться, что для Unity задан тип пространства отслеживания **румскале** . Хотя Румскале является значением по умолчанию, необходимо явно задать его и убедиться, что вы получаете значение true, чтобы выявить ситуации, в которых пользователь переместил компьютер за пределы разкалиброванной комнаты.

```cs
if (XRDevice.SetTrackingSpaceType(TrackingSpaceType.RoomScale))
{
    // RoomScale mode was set successfully.  App can now assume that y=0 in Unity world coordinate represents the floor.
}
else
{
    // RoomScale mode was not set successfully.  App cannot make assumptions about where the floor plane is.
}
```

После того как приложение успешно установит тип пространства отслеживания Румскале, на этаж будут отображаться содержимое, помещенное на плоскости y = 0. Источник в точке (0, 0, 0) будет определять конкретное место в этаже, где пользователь стояли во время настройки комнаты, с параметром-Z, представляющим Направление переадресации во время установки.

В коде скрипта можно вызвать метод Трижетжеометри, так как тип UnityEngine. экспериментальный. XR. граничное используется для получения граничного многоугольника, указывая тип границы Траккедареа. Если пользователь определил границу (вы получаете список вершин), вы узнаете, как можно обеспечить пользователю **возможности масштабирования комнаты** , где он может пройти по создаваемой сцене.

Обратите внимание, что система автоматически визуализирует границу, когда пользователь его приближает. Приложению не нужно использовать этот многоугольник для отрисовки самой границы.

Дополнительные сведения см. на странице [системы координат на Unity](coordinate-systems-in-unity.md) .

Некоторые приложения используют прямоугольник для ограничения их взаимодействия. Получение самого крупного вписанный прямоугольника напрямую не поддерживается в API UWP или Unity. В примере кода, приведенном ниже, показано, как найти прямоугольник в пределах отслеживаемых границ. Он основан на эвристике, поэтому не может найти оптимальное решение, однако результаты обычно соответствуют ожиданиям. Параметры в алгоритме можно настроить для поиска более точных результатов по затратам времени на обработку. Алгоритм находится в вилке набора средств Mixed Reality, который использует версию Unity МРТП Preview версии 5,6. Это недоступно для общего доступа. Код должен быть напрямую использован в 2017,2 и более поздних версиях Unity. Код будет перенесен на текущий МРТК в ближайшем будущем.

[ZIP-файл кода на GitHub](https://github.com/KevinKennedy/MixedRealityToolkit-Unity/releases/tag/5.6.MRTP20) Важные файлы:
* Assets/Холотулкит/Stage/Scripts/Стажеманажер. CS-пример использования
* Assets/Холотулкит/Stage/Scripts/Ларжестректангле. CS-реализация алгоритма
* Assets/Холотулкит-UnitTests/Editor/Stage/Ларжестректанглетест. CS-тривиальный тест алгоритма

Пример результатов:

![Пример результатов](images/largestrectangle-400px.jpg)

Алгоритм основан на блоге, Даниэль Смилков: [самый крупный прямоугольник в многоугольнике](https://d3plus.org/blog/behind-the-scenes/2014/07/08/largest-rect/)

### <a name="unity-step-9-work-through-your-input-model"></a>Unity шаг 9. Работа с входной моделью

Каждая игра или приложение, предназначенное для существующего ХМД, будет иметь набор входных данных, которые он обрабатывает, типы входных данных, необходимые для работы, и конкретные интерфейсы API, которые он вызывает для получения этих входных данных. Мы реализовали попытку сделать это как можно проще и простым, чтобы воспользоваться преимуществами входных данных, доступных в Windows Mixed Reality.
1. Ознакомьтесь с **[руководством по использованию входных данных для Unity](input-porting-guide-for-unity.md)** , чтобы узнать, как Windows Mixed Reality предоставляет входные данные, и как они сопоставлены с тем, что приложение может сделать сегодня.
2. Выберите, следует ли использовать входной API Unity для перекрестной виртуальной/VR-SDK или специальный входной API для MR. Общие входные API-интерфейсы input. "input. Axis" используются в приложениях Unity VR сегодня для [Окулус входных](https://docs.unity3d.com/Manual/OculusControllers.html) и [опенврных входных](https://docs.unity3d.com/Manual/OpenVRControllers.html)данных. Если ваши приложения уже используют эти API для контроллеров движения, это самый простой путь — необходимо просто сопоставить кнопки и оси в диспетчере ввода.
    * Доступ к данным контроллера движения в Unity можно получить с помощью общих API-интерфейсов input.-Button/input. UnityEngine или метода MR. input. (ранее в пространстве имен UnityEngine. XR. WSA. input в Unity 5,6)
    * См. [пример в разделе набор средств](https://github.com/Microsoft/HoloToolkit-Unity/pull/572) , объединяющий контроллеры планшета и движения.

### <a name="unity-step-10-performance-testing-and-tuning"></a>Unity шаг 10. Тестирование и настройка производительности

Windows Mixed Reality будет доступна на широком классе устройств, от высокопроизводительных компьютерных ПК до широкого спектра основных ПК на рынке. В зависимости от того, на каком рынке ориентирован целевой объект, существует существенная разница в доступных вычислениях и графиках графики для вашего приложения. Во время этого упражнения по переносу вы, скорее всего, используете ПК уровня "Премиум" и имели значительные бюджетные и графические графики, доступные для вашего приложения. Если вы хотите сделать приложение доступным более широкой аудитории, следует протестировать и профилировать приложение на [целевом оборудовании, которое вы хотите](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines)использовать.

[Unity](https://docs.unity3d.com/Manual/Profiler.html) и [Visual Studio](https://docs.microsoft.com/visualstudio/profiling/index) включают в себя Профилировщики производительности, а как [Корпорация Майкрософт](understanding-performance-for-mixed-reality.md) , так и [Корпорация Intel](https://software.intel.com/articles/vr-content-developer-guide) публикуют рекомендации по профилированию и оптимизации производительности. Существует подробное обсуждение производительности, доступное [для понимания производительности смешанной реальности](understanding-performance-for-mixed-reality.md). Дополнительные сведения о Unity см. в разделе [рекомендации по повышению производительности для Unity](performance-recommendations-for-unity.md).

## <a name="see-also"></a>См. также
* [Руководство по переносу логики ввода для Unity](input-porting-guide-for-unity.md)
* [Минимальные рекомендации по совместимости Windows Mixed Reality с оборудованием ПК](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines)
* [Основные сведения о производительности смешанной реальности](understanding-performance-for-mixed-reality.md)
* [Рекомендации по повышению производительности для Unity](performance-recommendations-for-unity.md)
* [Добавление поддержки Xbox Live в Unity для UWP](https://docs.microsoft.com/windows/uwp/xbox-live/get-started-with-partner/partner-add-xbox-live-to-unity-uwp)
