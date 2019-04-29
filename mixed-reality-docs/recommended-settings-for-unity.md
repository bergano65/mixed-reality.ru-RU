---
title: Рекомендуемые параметры для Unity
description: Unity предоставляет несколько функций, характерных для смешанной реальности, который может быть переключен в параметрах проекта.
author: Troy-Ferrell
ms.author: trferrel
ms.date: 03/26/2019
ms.topic: article
keywords: Unity, параметры, смешанной реальности
ms.openlocfilehash: a67c3a65819855be6d43941c05f9a0027abf2f6d
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600156"
---
# <a name="recommended-settings-for-unity"></a>Рекомендуемые параметры для Unity

Среда Unity предоставляет набор параметров по умолчанию, которые обычно представляют собой усредненной ситуации для всех платформ. Тем не менее Unity предоставляет несколько функций, характерных для смешанной реальности, который может быть переключен в параметрах проекта.

## <a name="performant-environment-set-up"></a>Настройки среды высокой производительностью

### <a name="low-quality-setting"></a>Параметр низкое качество

Очень важно изменить **Unity качество** для среды, чтобы **«быстрый»**. Это поможет убедиться, что приложение запущено performantly в соответствующий текущей частоты кадров. Это крайне важно для разработки Hololens. Для разработки на иммерсивную, в зависимости от спецификации рабочего стола, обеспечения работы интерфейс виртуальной Реальности по-прежнему позволяет достичь частоте кадров без наименьшее параметров качества. 

В Unity 2018 LTS +, уровень качества проекта задаются:

В разделе **изменить** > **параметры проекта** > **качества** > задать **по умолчанию** , щелкнув Стрелка вниз, чтобы **Fastest** уровень качества

### <a name="single-pass-instancing-rendering-path"></a>Отрисовки путь один проход для создания экземпляров

В приложениях смешанной реальности сцены визуализируется дважды, один раз для каждого глаза для пользователя. По сравнению с традиционной разработкой 3D, это фактически две объем работы, которую необходимо вычислить. Таким образом важно выбрать наиболее эффективный путь подготовки к просмотру в Unity, чтобы сохранить на время ЦП и GPU. Один проход внутренне отрисовки оптимизирует конвейер отрисовки Unity для смешанной реальности приложений и поэтому рекомендуется включить этот параметр по умолчанию для каждого проекта. 

Чтобы включить эту функцию в проекте Unity
1)  Откройте **параметры проигрывателя XR** (перейдите к **изменить** > **параметры проекта** > **проигрывателя**  >  **XR параметры**)
2) Выберите **экземпляры одного передать** из **стерео метод визуализации** раскрывающееся меню (**поддерживается виртуальной реальности** должен быть установлен флажок)

Дополнительные сведения при таком подходе подготовки к просмотру, ознакомьтесь со следующими статьями из Unity.
- [Как добиться максимальной производительности AR и VR с расширенный рендеринг стерео](https://blogs.unity3d.com/2017/11/21/how-to-maximize-ar-and-vr-performance-with-advanced-stereo-rendering/)
- [Создание экземпляров однократного прохода](https://docs.unity3d.com/Manual/SinglePassInstancing.html) 

>[!NOTE]
> Один распространенная проблема с одной передавать экземпляры отрисовки возникает, если разработчики уже есть существующие пользовательскими шейдерами, не написаны для создания экземпляров. После включения этого компонента, разработчики заметить некоторые объекты Gameobject только визуализации, в один глаз. Это обусловлено тем, связанных пользовательскими шейдерами, не имеют соответствующих свойств для создания экземпляров.
>
> См. в разделе [единый передать стерео отрисовки для HoloLens](https://docs.unity3d.com/Manual/SinglePassStereoRenderingHoloLens.html) из Unity способов решения этой проблемы

### <a name="enable-depth-buffer-sharing"></a>Включить совместное использование буфера глубины

Чтобы обеспечить большую стабильность голограмма из согласно восприятию пользователя, рекомендуется включить **совместное использование буфера глубины** свойство в Unity. Если этот флажок установлен, Unity будет совместно использовать карты глубины, созданный приложением на платформе Windows смешанной реальности. Платформа, затем будет для оптимизации стабильности голограмма специально для сцены для любого заданного интервала, отображаемого в приложении.

Чтобы включить эту функцию в проекте Unity
1) Откройте **параметры проигрывателя XR** (перейдите к **изменить** > **параметры проекта** > **проигрывателя**  >  **XR параметры**)
2) Установите флажок для **разрешить общий буфер глубины** под **виртуальной реальности SDK** > **Windows Mixed Reality** расширения (**виртуальной Поддерживается реальности** должен быть установлен флажок)

Кроме того, рекомендуется выбрать **16-битовая глубина** под **формат глубина** настройки в этой панели, особенно для разработки Hololens. Выбрав 16-разрядное по сравнению с 24-разрядный значительно снизить требования к пропускной способности, — меньше данных понадобится переместить/обработки.

>[!NOTE]
> Разработчикам следует Имейте в виду борьба с Z при изменении этих значений, а также параметры практически/дальней плоскости камеры. Борьба с Z возникает при двух объекты gameobject для подготовки к просмотру и тому же пикселу и из-за ограничений в точности буфер глубины (т. е. глубина z), Unity не может понять, какой объект находится перед другим. Обратите внимание разработчикам мерцание между двумя объектами игры, как только они *бороться* для одного значения z-depth. Это можно решить путем переключения на формат 24-битовую глубину, благодаря наличию более широкий диапазон значений для каждого объекта, для расчета при их z-depth от камеры.
>
> Тем не менее рекомендуется, особенно для Hololens разработки, чтобы изменить камеры, практически и гораздо вместо плоскостей меньший диапазон и сохраняя 16-битовая глубина форматирования. Z-depth не линейно сопоставляется диапазон значений вдоль камеры ближней и дальней плоскости. Такое поведение можно изменить, выбрав *Main Camera* в сцене и в разделе **инспектор**, изменить **ближайшем & далеко обрезки плоскости** значениям для уменьшения их диапазона (например) из 1000 m для 100 млн строк или другой значение x и т.д.)

### <a name="building-for-il2cpp"></a>Создание продукта для IL2CPP

Unity устаревшим поддержка сценариев серверной части и, следовательно, разработчикам рекомендуется использовать .NET **IL2CPP** для их UWP сборка в visual studio. Несмотря на то, что это дает различные преимущества, построение решения visual studio из Unity для **Il2CPP** может быть значительно медленнее, чем старый метод .NET. Таким образом, настоятельно рекомендуется следовать рекомендации по созданию **IL2CPP** для сохранения на время разработки итерации.

1) Используйте инкрементное построение, построение проекта в тот же каталог на каждый раз заново с помощью предварительно созданных файлов существует
2) Отключить сканирование программного обеспечения защиты от вредоносных программ для проекта & построить папки
   - Откройте **защиты от вирусов и угроз** в разделе параметров приложения Windows 10
   - Выберите **Управление параметрами** под **параметры защиты от вирусов и угроз**
   - Выберите **Установка и удаление исключений** под **исключения** раздел
   - Нажмите кнопку **добавьте исключение** и выводит выберите папки содержат код проекта Unity и сборки
3) Использовать SSD для построения

См. в статье [Оптимизация времени сборки для IL2CPP](https://docs.unity3d.com/Manual/IL2CPP-OptimizingBuildTimes.html) Дополнительные сведения.

## <a name="publishing-properties"></a>Свойства публикации

### <a name="holographic-splash-screen"></a>Экран-заставка holographic

HoloLens имеет класс mobile ЦП и GPU, это означает, что приложения может занять немного больше времени на загрузку. При загрузке приложения пользователи будут видеть только черного и поэтому они может возникнуть вопрос, что происходит. Чтобы заверить их во время загрузки, можно добавить holographic заставки.

Для переключения на экране-заставке holographic:
1) Перейдите к **изменить** > **параметры проекта** > **проигрывателя** страницы
2) Щелкните **Windows Store** вкладку и откройте **изображение заставки** раздел
3) Применить нужный образ в разделе **Windows Holographic > Holographic изображение заставки** свойство.
    - Включение и выключение **Показать экран-заставка Unity** параметр будет включить или отключить заставку Unity фирменной символикой. Если у вас лицензия Unity Pro, Unity, типизированной экран-заставка всегда отображается.
    - Если **Holographic изображение заставки** будет применен, он всегда отображается независимо от того, включен или отключен флажок Показать экран-заставка Unity. Указание образа заставкой holographic доступна только для разработчиков с лицензией Unity Pro.

|  Показать экран-заставка Unity  |  Изображение holographic-заставки  |  Поведение |
|----------|----------|----------|
|  Включено  |  Нет  |  Отображение экрана-заставки по умолчанию Unity 5 секунд или пока приложение будет загружено, какой срок больше. | 
|  Включено  |  Настраиваемое  |  Показать экран-заставка пользовательского 5 секунд или пока приложение будет загружено, какой срок больше. | 
|  Отключено  |  Нет  |  Показать прозрачный черный (nothing), пока приложение будет загружено. | 
|  Отключено  |  Настраиваемое  |  Показать экран-заставка пользовательского 5 секунд или пока приложение будет загружено, какой срок больше. | 

См. в статье [документации Unity экран-заставка](https://docs.unity3d.com/Manual/class-PlayerSettingsSplashScreen.html) Дополнительные сведения.

### <a name="tracking-loss"></a>Отслеживание потери

Гарнитуры смешанной реальности зависит от того, отображаются вокруг него для создания среды [заблокирован в мире систем координат](coordinate-systems-in-unity.md), которая разрешает голограммы остаются в позиции. При гарнитура не сможет найти сам мира, говорят гарнитура *потери отслеживания*. В этом случае функциональные возможности зависят от блокировки world координат систем, таких как пространственных этапы, пространственных привязки и пространственное сопоставление не работают.

Если происходит потеря отслеживания, поведение по умолчанию Unity — голограммы отрисовки останавливать, приостанавливать [цикла игры](http://docs.unity3d.com/Manual/ExecutionOrder.html), и отслеживания потери уведомлений удобно то выглядит взглядом пользователей. Пользовательские уведомления могут также предоставляться в виде отслеживания потери образа. Для приложений, которые зависят от отслеживания для взаимодействия с ними целиком достаточно позволяет обрабатывать это полностью, пока не освобождается отслеживания Unity. Разработчики могут передать пользовательский образ для отображения во время отслеживания потери. 

Чтобы настроить образ потеряны отслеживания:
1) Перейдите к **изменить** > **параметры проекта** > **проигрывателя** страницы
2) Щелкните **Windows Store** вкладку и откройте **изображение заставки** раздел
3) Применить нужный образ в разделе **Windows Holographic > отслеживания потери изображение** свойство.

#### <a name="opt-out-of-automatic-pause"></a>Отказаться от автоматической приостановки

Некоторые приложения могут не требовать отслеживания (например [приложений с доступом только ориентации](coordinate-systems-in-unity.md) такие как средства просмотра видео 360 градусов) или может потребоваться продолжить обработку без перерыва во время отслеживания теряется. В таких случаях приложения можно отказаться от потери отслеживание поведения по умолчанию. Разработчики, выберите этот параметр, ответственность за любые объекты, которые не будут отображаться должным образом в случае потери отслеживания скрытие и отключение. В большинстве случаев только содержимое, которое рекомендуется использовать для подготовки к просмотру, в том, что случай — блокировки текст содержимого, относятся к главной камеры.

Чтобы отказаться от автоматической приостановки поведение:
1) Перейдите к **изменить** > **параметры проекта** > **проигрывателя** страницы
2) Щелкните **Windows Store** вкладку и откройте **изображение заставки** раздел
3) Изменить **Windows Holographic > на Приостановка потери отслеживания и отображения изображения** флажок.

#### <a name="tracking-loss-events"></a>Потеря событий отслеживания

Чтобы определить пользовательское поведение при потере отслеживания, обрабатывать глобальный [потери событий отслеживания](tracking-loss-in-unity.md).

### <a name="capabilities"></a>Возможности

Для приложения, чтобы воспользоваться преимуществами некоторых функций его необходимо объявить соответствующие возможности в манифесте. Манифеста объявления можно сделать в Unity, поэтому они будут включены в каждый проект последующих экспорта. 

Возможности можно включить для приложения смешанной реальности по:
1) Перейдите к **изменить** > **параметры проекта** > **проигрывателя** страницы
2) Щелкните **Windows Store** вкладку и откройте **параметров публикации** раздела и искать **возможности** списка

Применимые возможности для включения часто используемые интерфейсы API для Holographic приложений являются:
<br>

|  Возможности  |  API, требующие возможности |
|----------|----------|
|  SpatialPerception  |  SurfaceObserver | 
|  Веб-камера  |  PhotoCapture и VideoCapture | 
|  PicturesLibrary или VideosLibrary  |  PhotoCapture или VideoCapture, соответственно (при хранении записанного содержимого) | 
|  Микрофон  |  VideoCapture (при записи аудио), DictationRecognizer, GrammarRecognizer и KeywordRecognizer | 
|  internetClient  |  DictationRecognizer (и использовать Unity Profiler) | 

## <a name="see-also"></a>См. также
* [Общие сведения о разработке Unity](unity-development-overview.md)
* [Производительность Understaing для смешанной реальности](understanding-performance-for-mixed-reality.md)
* [Рекомендации по производительности для Unity](performance-recommendations-for-unity.md)