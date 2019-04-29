---
title: Практический пример — Создание перспектив невозможно для HoloTour
description: Нам требовалось своим опытом в HoloTour для Microsoft HoloLens быть unforgettable. Помимо традиционных туристов останавливается мы планировали out некоторые «невозможно перспективы».
author: DannyAskew
ms.author: daaske
ms.date: 03/21/2018
ms.topic: article
keywords: Windows HoloTour, HoloLens, смешанной реальности
ms.openlocfilehash: be00df73543aa295e1e0dbe1462a888d6bb24954
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600116"
---
# <a name="case-study---creating-impossible-perspectives-for-holotour"></a>Практический пример — Создание перспектив невозможно для HoloTour

Нам требовалось своим опытом в HoloTour для Microsoft HoloLens быть unforgettable. Помимо традиционных туристов останавливается мы планировали out некоторые «невозможно перспектив —» секунд, может быть организовано в работе любой Обзор, но с помощью технологии в HoloLens, мы может выводить непосредственно в гостиной. Создание содержимого для этих функций требуется некоторые различные методики, чем наш процесс отслеживания standard.

## <a name="the-content-challenge"></a>Запрос содержимого

Существуют определенные сцен в интерфейсе HoloTour, такие как выноске горячий воздух являются надстройками над рим современного и гладиаторских борьбе с Colosseum в древних Рим —, которые предоставляют уникальные представления, вы не увидите в любом другом месте. Эти моменты предназначены для по вкусу и удивить своих вы, ваши подключение через HoloTour больше, чем просто интерфейс образовательных. Они являются секунд, мы хотим, чтобы запомнить и переживать нужно сообщить другим пользователям об вы. Так как мы не занимают нашей платформе камеры в небо и (пока), мы еще не происходит переход во времени, каждая из этих «невозможно точек зрения» вызывается специальные подход к созданию содержимого.

## <a name="behind-the-scenes"></a>Как это делается

Создание этих уникальный секунд и перспектив, требуется больше, чем просто съемки и редактирования. Она заняла огромного количества времени, людей с различные уровни опыта и небольшой фрагмент Hollywood magic.

### <a name="viewing-rome-from-a-hot-air-balloon"></a>Просмотр рим из всплывающей горячего воздуха

Из наших планирования заре мы поняли, что мы хотели сделать воздуха в HoloTour. Возможность наблюдать множество рим с неба дает перспективы, большинство людей никогда не о том и понять, насколько популярны ориентиров расположены пространственно. Захвате это самостоятельно с помощью наших существующих камеру и микрофон тестовой платформы были бы очень сложно, но к счастью избавиться от необходимости.

Во-первых важно объяснить, в них все расположения, которые вы посещаете в HoloTour иметь перемещения. Нашей целью было в качестве «воспринимается как действительно осталось» и так как заключены в перемещения всюду в реальной жизни, наш виртуальный назначения, необходимых для передачи также окружения перемещения. Например при посещении Pantheon в поездке, вы увидите люди никогда во всей площади и сосредотачиваются на действия. Движение фона помогает вам кажется, что Вы действительно закончили изучение в расположении, а не в промежуточной среде с статический.

Чтобы создать воздуха выполнил выноски, мы сотрудничаем с другими командами корпорации Майкрософт, чтобы получить доступ к аэрофотоснимков панорамное рим. Качество этих изображений был отличным представление было впечатляющие, но когда мы использовали их в фоновом режиме без изменений, они посчитали lifeless по сравнению с другими частями демонстрации и отсутствие motion было отвлекает. 


![Горячий воздух всплывающей корзины, с плавающей запятой через рим.](images/hotairballoon1-300px.png)<br>
*В корзину всплывающей горячего воздуха, с плавающей запятой через рим*

Чтобы убедиться, что воздушный расположений выполняется та же панель качества, как другие назначения, мы решили преобразования статический фотографии в жизни, перемещение сцены. Первым шагом было изменить образ и составных движения в него. Мы подрядчиком исполнителя визуальные эффекты, которые помогут нам в этом. Изменение было сделано для медленно именно облаков, птиц, некоторые вещи и случайных плоскости или вертолетом, проходящий через skyline. На землю количество машин, были внесены диска улицы. Если вы уже на этом Обзор рим в HoloTour, маловероятно, что вы были явным образом узнает об этом движения. Это действительно здорово! Слабая движение не предназначен для перехвата руку, но без этих мало штрихи, люди заметили немедленно что было статическое изображение в сцене.

Вторая вещь, которую мы сделали было задать точку зрения из которого необходимо просмотреть сцену. Вы не почувствовать себя нужна только если возможно, вы просто с плавающей запятой в midair, поэтому мы создали трехмерной модели всплывающей и можно разместить внутри него. Это позволяет сильна выноске и найдите на границу для получения более зрения. Мы обнаружили, это может быть естественным и удобным способом добиться аэрофотоснимков.

Интерфейс всплывающей горячий воздух представлен уникальные задачи для нашей звуковой команды в виде логистики позволила нам необходимости микрофоны тысячи футов при наведении рим. К счастью у нас было много окружения записи звука из по всему, нам удалось использовать во время эксплуатации по городу. Мы разместили аудио отправители на их относительные расположения, из которой они были записаны с нуля. Аудио затем был отфильтрован, чтобы звук, находящегося далеко, как если бы вы полной его с точки зрения пользователя, даже в выноске горячий воздух обеспечение soundscape подлинный, направленных на сцене.

### <a name="time-traveling-to-ancient-rome"></a>Времени в дороге к древних рим

Оставшиеся файлы скульптур и зданий во всей рим впечатляют даже две тысячи лет после их создания, но мы знали, что у нас было уникальную возможность показать, что это привело бы к вернуться назад во времени и см. в статье эти структуры в древних рим.

Естественно, не все видеоматериала или статические изображения) из Colosseum с момента ее появления при его создании, так что нам требовалось создать собственную. Мы решили исправить много узнать все о структуре, как мы могли бы; Основные сведения о материалов он был сделан из, просмотр архитектурных схем и чтение описания исторических получить достаточно информации, чтобы иметь возможность создания виртуальных отдых. 

![Ruins современного из Colosseum с наложенной на нее, указывая floor решают, пока он выглядел бы в древних рим.](images/rome-colosseum-overlay-500px.png)<br>
*Ruins современного из Colosseum с наложенной на нее, указывая floor решают, пока он выглядел бы в древних рим*

Первое, что нам нужно было улучшить традиционные обзоры с образовательным наложения. В HoloTour при посещении ruins Colosseum как ситуации на сегодняшний день, решают floor применяется Показать, как он выглядел бы во время использования, включая сложных нелегальным промежуточной области. Обычный освещает возможно, эти сведения, описанные для вас и может попытаться придумать, но в HoloTour можно увидеть его.

Для наложения так у нас было наших исполнители сопоставить точки зрения нашей записи материал и вручную создать изображение для наложения. Точки зрения должно соответствовать таким образом, когда мы заменить видео наш образ, оба будут выравниваться должным образом.

### <a name="staging-the-gladiator-fight"></a>Промежуточные борьбе gladiator

Хотя наложений привлекательных способ рассказать пользователям о журнале, что мы были самой важной новинкой передачи вы назад во времени. Наложение была просто по-прежнему образ с определенной точки зрения, но времени в поездках потребует всей Colosseum, которые нужно моделировать и, как уже говорилось ранее, были нужны движения в сцене, чтобы сделать это проверки активности. Это занимает значительный объем усилий.

Этого начинания слишком велико для нашей команде, отдельно, поэтому наша группа картинок, работали с Whiskytree внешних эффектов компании, который обычно работает на визуальные эффекты для Hollywood фильмов. Whiskytree помогли нам воссоздать Colosseum в его heyday, что позволило нам помогают изучить структуру при положение на площадке решают и создание представления борьбе gladiator из поля императора. Была crowds и машет баннеров добавлять небольшие движения, необходимо будет восприниматься как реальных местах и не только изображения.

![Повторно созданная Colosseum материал из floor решают. При просмотре в HoloTour титульные flutter в очень просто, предоставляя чувство движения.](images/recreated-colosseum-holotour-500px.png)<br>
*Повторно созданная Colosseum материал из floor решают. При просмотре в HoloTour титульные flutter в очень просто, предоставляя чувство движения.*

Примером рим завершающийся с борьбе gladiator. Whiskytree состав нам решают и 3D рекордное моделирования, отображаемой в качестве видео, но нам нужно было добавить в gladiators на площадке решают. Это часть нашей работы было больше похожи Hollywood производства видео, чем проект из руковожу game studio. Членам нашей команды отображенные грубого борьбе последовательности, а затем уточняется его с choreographer. Мы субъектов для промежуточного хранения наших макетов дела на работу и приобрели armor, чтобы они выглядели части. Наконец мы расположенным всей сцены с зеленый экран.

![Наши gladiators начало инструкции между принимает.](images/green-screen-gladiators-holotour-500px.jpg)<br>
*Наши gladiatiors, начало инструкции между принимает*

Этой сценой расположениях, в которых в поле императора в том, что означает, что все материал, должен был быть с этой точки зрения. Если мы расположенным из которых борьба gladiators на площадке решают, мы не смогли правильно составного борьбе последовательность в более поздней версии, поэтому мы реализовали наших оператор камеры в точности прогноза слишком высокие отсечения, глядя вниз в последовательности борьбе для съемки.

![Начало правой точки зрения: съемки из отсечение точности прогноза.](images/scissor-lift-holotour-500px.jpg)<br>
*Начало правой точки зрения: съемки из точность отсечения*

В эксплуатации, gladiators были составных на пол решают точки зрения была выполнена без ошибок, но отображается как одна проблема: тени gladiators на зеленый экран были удалены в ходе процесса компоновки. Без тени оно выглядело, как gladiators повторяющие в воздухе. К счастью Whiskytree отлично решить только подобные проблемы и их использовать немного технические способности Добавление теней обратно в нашей сцены. Результатом является, отображаемые в учебнике уже сегодня.

## <a name="about-the-authors"></a>Об авторах

<table style="border:0">
<tr>
<td style="border:0" width="60px"> <img alt="David Haley" width="60" height="60" src="images/haley.png" /></td>
<td style="border:0" width="408"> <b>Дэвид Хейли</b> — старший разработчик, узнали о платформ камеры и воспроизведение видео, чем он думал, можно работать с HoloTour.</td>

<td style="border:0" width="60px"> <img alt="Jason Syltebo" width="60" height="60" src="images/syltebo.png" /></td>
<td style="border:0" width="408"> <b>Джейсон Syltebo</b> — конструктор аудио, кто выполняет проверку того, вы можете столкнуться с soundscape каждого назначения, которые вы посещаете, даже в том случае, если вернуться назад во времени.</td>
</tr>
<tr>
<td style="border:0" width="60px"> <img alt="Danny Askew" width="60" height="60" src="images/askew.png" /></td>
<td style="border:0" width="408"> <b>Дэнни Askew</b> является видео исполнителя удостоверился, что исследование рим был как подавая максимально.</td>

<td style="border:0" width="60px"></td>
<td style="border:0" width="408"></td>
</tr>
</table>


## <a name="see-also"></a>См. также
* [Видео: Microsoft HoloLens: HoloTour](https://www.youtube.com/watch?v=pLd9WPlaMpY)