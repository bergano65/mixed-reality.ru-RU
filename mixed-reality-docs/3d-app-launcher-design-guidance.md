---
title: Руководство по проектированию приложения трехмерной запуска
description: Запуск приложения трехмерной является «физический» объектом в смешанной реальности домик пользователя, который пользователи могут выбрать для запуска приложения.
author: thmignon
ms.author: thmignon
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality, разработки, запуска трехмерных приложений, иммерсивных гарнитура live куба
ms.openlocfilehash: 47db5bffa121c0cc11d246dc749c464e5f187270
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59598549"
---
# <a name="3d-app-launcher-design-guidance"></a>Руководство по проектированию приложения трехмерной запуска

Поместить на гарнитуры смешанной реальности Windows иммерсивных (VR), вводится Windows Mixed Reality дома, представить в виде дом на со скалы заключенных в горы и воды (хотя вы можете [выберите других средах и даже создавать собственные](add-custom-home-environments.md)). В пространстве это дома, пользователь может упорядочивания и организации трехмерные объекты и приложения, которые их интересуют любым способом, нужные им. Объект **запуска трехмерных приложений** — объект «физический» пользователь смешанном реальности домик, который пользователи могут выбрать для запуска приложения.

![Пример: Floaty запуска Bird трехмерных приложений](images/20171016-151526-mixedreality1-1200px-1000px.jpg)<br>
*Пример запуска трехмерного приложения floaty Bird (вымышленной приложение)*

## <a name="3d-app-launcher-creation-process"></a>Процесс создания приложения трехмерной запуска

Существует 3 шага к созданию запуска трехмерных приложений:
1. Проектирование и concepting (Эта статья)
2. [Моделирование и экспорт](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md)
3. Интеграции его в приложении:
    * [Приложения UWP](implementing-3d-app-launchers.md)
    * [Приложения Win32](implementing-3d-app-launchers-win32.md)

## <a name="design-concepts"></a>Принципы проектирования

### <a name="fantastic-yet-familiar"></a>Отлично, но знакомый

Живет в средстве запуска приложений в Windows Mixed Reality среды — часть знакомых, часть фантастических/sci-fi. Лучшие средства запуска следуют правилам этот мир. Можно рассматривать как можно занять объект знакомая и репрезентативной из приложения, но приспособить некоторые правила фактическое реальностью. Волшебная приведет к.

### <a name="intuitive"></a>Интуитивно понятный

Если взглянуть на ваши средства запуска приложений, его назначение — для запуска приложения - должно быть очевидно и не будет вызывать путаницу. Например убедитесь, что ваши средства запуска является очевидным достаточно представителем своего приложения, не следует путать части обстановки в доме со скалы. В средстве запуска приложений следует пригласить участников сенсорного ввода или выбирать его.

![Пример: Новые средства запуска приложения трехмерной Примечание](images/20171016-152145-mixedreality1-1200px-1000px.jpg)<br>
*Пример запуска трехмерного приложения новой Примечание (вымышленной приложение)*

### <a name="home-scale"></a>Домашний масштабирования

Средствах запуска приложений 3D live со скалы дома и их размер по умолчанию должна быть вам понятной относительно других объектов «физический» в пространстве. Если ваши средства запуска рядом с полем, скажем, на предприятии дома или некоторые мебель, все должно быть дома, size-wise. Чтобы посмотреть, как он выглядит в сантиметрах 30 третьего, но помните, что пользователям можно масштабировать его вверх или вниз при является хорошей отправной точкой.

### <a name="own-able"></a>Может владеть

Средство запуска приложений следует считать объект, который пользователь будет рады принять в своем пространстве. Они будут практически вокруг сами подобными вещами, поэтому средство запуска должно быть так, как будто мысль пользователя было достаточно желательным, поиска и оставить рядом.

![Пример: Средство запуска Astro деформации трехмерных приложений](images/20171016-132936-mixedreality-1200px-1000px.jpg)<br>
*Пример запуска трехмерного приложения Astro Warp (вымышленной приложение)*

### <a name="recognizable"></a>Распознаваемые

Средство запуска вашего приложения трехмерной мгновенно должна отображать «приложения-brand» пользователям, см. в разделе, он. Если в приложении имеется символ типа "звезда" или объект особенно характера, рекомендуется использовать, как часть проекта. В современном мире, смешанной реальности объект будет рисования больший интерес от пользователей, чем просто логотип отдельно. Узнаваемых объектов взаимодействия торговой марки, легко и быстро.

### <a name="volumetric"></a>Объемные

Приложение заслуживает больше, чем просто поместить ваш логотип на плоскость и чем уверовать. Ваши средства запуска следует считать замечательных, 3D и физического объекта в пространстве пользователя. Представьте, что приложение будет иметь всплывающую в первые ряды Парада День благодарения Macy — Хороший подход. Задайте себе вопрос: что бы действительно wow людей как он указан на улице? Будет выглядеть отлично со всех сторон просмотра?


:::row:::
    :::column:::
        ![Logo only](images/20171016-140436-mixedreality-640px.jpg)
        *Logo only*
    :::column-end:::
    :::column:::
        ![More recognizable with a character](images/20171016-140557-mixedreality-640px.jpg)
        *More recognizable with a character*
    :::column-end:::
:::row-end:::


:::row:::
    :::column:::
        ![Flat approach, not surprisingly, feels flat](images/20171016-155101-mixedreality-640px.jpg)
        *Flat approach, not surprisingly, feels flat*
    :::column-end:::
    :::column:::
        ![Volumetric approach better showcases your app](images/20171016-161407-mixedreality-640px.jpg)
        *Volumetric approach better showcases your app*
    :::column-end:::
:::row-end:::


## <a name="tips-for-good-3d-models"></a>Советы по хорошие трехмерной модели

### <a name="best-practices"></a>Рекомендации
* При планировании аналитики для запуска вашего приложения, ограничить это примерно 30cm куба. Таким образом, 1: соотношением 1:1.
* Модели должны быть уровнем ниже 10 000 многоугольников. [Дополнительные сведения о треугольник счетчики и уровни подробности (LODs)](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md#triangle-counts-and-levels-of-detail-lods)
* Проверка в иммерсивных гарнитура, когда это возможно.
* Сведения о сборке в вашей модели geometry, где это возможно, не полагайтесь на текстур для детализации.
* Создание геометрического объекта в «water тесной» закрыто. Нет дыр, которые не моделируются в.
* Используйте natural материалы в объекте. Представьте себе, создания его в реальном мире.
* Убедитесь, что модель считывает хорошо на различных расстояниях и размеры.
* Когда модель готова к работе, чтение [Экспорт активы рекомендации](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md#asset-requirements-overview).

![Модель с тонких моментов в текстуре](images/20171013-143334-mixedreality-640px.jpg)<br>
*Модель с тонких моментов в текстуре*

### <a name="what-to-avoid"></a>Чего следует избегать
* Не используйте сведения о высокой контрастности или шаблоны небольшой, занят и текстур.
* Не использовать тонкую geometry-он не работают хорошо на расстоянии и будет плохо псевдоним.
* Не позволяйте частями модели расширения слишком много, помимо 1: соотношением 1:1. Он создаст проблемы масштабирования.

![Избегайте высокой контрастности, "мелкая" занят шаблоны](images/20171013-143603-mixedreality-640px.jpg)<br>
*Избегайте высокой контрастности, small, занят шаблоны*

## <a name="how-to-handle-type"></a>Как обрабатывать тип

### <a name="best-practices"></a>Рекомендации
* Мы рекомендуем вашего типа состоит из примерно треть из вашего средства запуска приложений (или больше). Тип — главное, что предоставляет сотрудникам идею, ваши средства запуска, на самом деле, запуска, поэтому весьма удобно, если это довольно значительной.
* Избежать создания очень широкий тип — попытаться сохранить его в пределах средствах запуска приложений core измерения (больше или меньше).
* Плоский тип можно работать, но имейте в виду, что он может быть трудно просмотреть определенные углами и в некоторых средах. Окончательная объемный предмет или backdrop за его, чтобы помочь в этом может потребоваться.
* Добавление измерений к типу выглядит неплохо в трехмерном пространстве. Заливка сторон типа другой, более темный оттенок цвета можно способствует повышению удобочитаемости.


:::row:::
    :::column:::
        ![Flat type without a backdrop can be hard to view from certain angles and in certain environments](images/flattype-640px.png)
        *Flat type without a backdrop can be hard to view from certain angles and in certain environments*
    :::column-end:::
    :::column:::
        ![Type with a built-in backdrop can work well](images/flattypeandbkg-640px.png)
        *Type with a built-in backdrop can work well*
    :::column-end:::
    :::column:::
        ![Extruded type can work well if you shade the sides](images/20171016-160221-mixedreality-640px.jpg)
        *Extruded type can work well if you shade the sides*
    :::column-end:::
:::row-end:::


**Тип цвета, которые работают**
* Белый
* Черный
* Ярко-частично насыщенный оттенок

![Тип цвета, которые работают.](images/20171016-112111-mixedreality-640px.jpg)<br>
*Тип цвета, которые работают*

### <a name="what-to-avoid"></a>Чего следует избегать

**Тип цвета, вызывающие проблемы**
* Среднего тона
* Серый
* Чрезмерно загруженных цветов или после приведения к серому цветов

![Тип цвета, вызывающие проблемы.](images/20171016-112246-mixedreality-640px.jpg)<br>
*Тип цвета, вызывающие проблемы*

## <a name="lighting"></a>Освещение

Освещение для запуска вашего приложения поступающие от среды со скалы дома. Не забудьте проверить ваши средства запуска в нескольких местах в помещении, так выглядит неплохо света и теней. Хорошая новость состоит, если вы выполнили другие рекомендации в этом документе, в средство запуска должен быть довольно правильно настроены для большинства освещения в доме со скалы.

Хорошим материалом для тестирования, как выглядят ваши средства запуска в различные источники света в среде являются Studio комнате мультимедиа, в любом месте за пределами и обратно во дворе дома (конкретные области с помощью пользуясь). Еще один хороший тест — поместить его в половину свет и тень половину и см. в разделе, как выглядит.

![Убедитесь, что ваши средства запуска вас устраивает света и теней.](images/20171013-145523-mixedreality-1200px-1000px.jpg)<br>
*Убедитесь, что ваши средства запуска вас устраивает света и теней*

## <a name="texturing"></a>Ускорение текстур

### <a name="authoring-your-textures"></a>Создание текстуры

Конечный формат вашего запуска трехмерных приложений будет файл .glb, который выполняется с помощью конвейера PBR (физически основе визуализации). Это может быть сложным процессом - пришло, пора использовать Технический исполнителя, если у вас еще нет. Если вас хватит смелости с НУЛЯ er, уделили [анализом и этой статье объясняется терминология PBR](http://wiki.polycount.com/wiki/PBR) и что происходит за кулисами, перед началом работы поможет вам избежать распространенных ошибок. 

![Пример: Примечание новые приложения](images/pbr-freshnote1-640px-500px.png)<br>
*Пример запуска трехмерного приложения новой Примечание (вымышленной приложение)*

**Рекомендуется использовать средство разработки**

Мы рекомендуем использовать [вещества образцу](https://www.allegorithmic.com/products/substance-painter) по Allegorithmic для создания окончательного файла. Если вы не знакомы с созданием шейдеров PBR в вещества художника, здесь [руководстве](https://docs.allegorithmic.com/documentation/display/SPDOC/Tutorials).

(Можно также [3D-Coat](https://3dcoat.com/home/), [Quixel Suite 2](https://quixel.se/suite2/), или [Marmoset Toolbag](https://www.marmoset.co/toolbag/) также будет работать, если вы более подробно ознакомиться с одним из них.)

### <a name="best-practices"></a>Рекомендации

* Если объект запуска вашего приложения был создан для PBR, оно должно быть довольно просто, для преобразования его в среде со скалы дома.
* Закрыть факсимильное наших шейдера ожидает рабочего процесса без операционной системы/неровности прежнюю Unreal PBR шейдера.
* При экспорте текстуры Сохранить [рекомендуемые размеры текстуры](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md#material-guidelines) в виду.
* Убедитесь, что для создания объектов для освещения в режиме реального времени — это означает, что:
    * Избегайте архивированные тени — или закрашиваемой shadows
    * Избегайте архивированные освещения в текстуры
    * Использовать один PBR материала, разработка пакетов, чтобы установить правой карты, созданные для наших шейдера

## <a name="see-also"></a>См. также

* [Создавать трехмерные модели для использования в смешанной реальности home](creating-3d-models-for-use-in-the-windows-mixed-reality-home.md)
* [Реализовать средствах запуска трехмерных приложений (приложения UWP)](implementing-3d-app-launchers.md)
* [Реализовать средствах запуска трехмерных приложений (приложения Win32)](implementing-3d-app-launchers-win32.md)