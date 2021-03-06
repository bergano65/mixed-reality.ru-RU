---
title: Меню руки
description: Меню руки позволяют пользователям быстро открыть пользовательский интерфейс, подключенный вручную, для часто используемых функций. Это практические рекомендации и рекомендации для меню вручную.
author: nbarragan23
ms.author: nobarr
ms.date: 08/27/2019
ms.topic: article
keywords: рука, меню, кнопка, быстрый доступ, макет
ms.openlocfilehash: 41a936d6041438c1cf1d8e4d4cc8cc30a5167491
ms.sourcegitcommit: 40b37104b0aec4554502dcc7dc430e340a6fa46a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "77092058"
---
# <a name="hand-menu"></a>Меню руки

![Расположение с улнар стороны](images/UX/UX_Hero_HandMenu.jpg)

Меню руки позволяют пользователям быстро открыть пользовательский интерфейс, подключенный вручную, для часто используемых функций. 

Ниже приведены лучшие методики, которые были найдены для меню вручную. Вы также можете найти пример сцены, демонстрирующий меню руки в [мртк](https://github.com/microsoft/MixedRealityToolkit-Unity/blob/mrtk_release/Documentation/README_Solver.md#hand-menu-with-handconstraint-and-handconstraintpalmup).

<br>

---

## <a name="behavior-best-practices"></a>Рекомендации по работе
О **. сохранить количество кнопок в маленьком виде:** из-за близкого расстояния между закрепленным меню и глазами пользователя, а также с тенденциями сосредоточиться на относительно небольшой визуальной области в любое время (особое внимание уделяется примерно 10 градусам), рекомендуется хранить небольшое количество кнопок. На основе нашего исследования один столбец с тремя кнопками хорошо работает, сохраняя все содержимое в поле View (фов), даже когда пользователь перемещает свои руки в центр фов. 

**Б. Использование меню "рука" для быстрого действия:** вызов ARM и обслуживание этой должности может легко вызвать выносливости ARM. Используйте метод, заблокированный вручную, для меню, для которого требуются короткие взаимодействия. Если меню является сложным и требует расширенного времени взаимодействия, рассмотрите возможность использования блокировки мира или блокировки текста. 

**В. угол на кнопке или панели:** меню должны касаться противоположного края и середины головки: Это позволяет естественным образом перемещаться к меню с противоположной рукой и позволяет избежать неприятностей или неудобных позиций при прикосновении к кнопкам. 

**Г. Рассмотрите возможность поддержки одноразовой или произвольной операции:** не следует рассчитывать, что обе руки пользователя всегда доступны. Рассмотрите широкий спектр контекстов, когда одна или обе руки недоступны, и убедитесь, что учетные записи разработки для этих ситуаций. Для поддержки однопользовательского меню можно попытаться перейти от руки к пункту меню, заблокированному вручную, при переворачивании вручную (идет перенос в карманный ПК). Для сценариев без участия рассмотрите возможность использования команды «Voice» для вызова кнопок меню руки.

**E. вызов из двух шагов:** если вы используете только событие "ручное" в качестве события для запуска меню "рука", оно может показаться ненужным, так как люди перемещают свои руки как можно больше (для взаимодействия и манипуляций с объектами) и случайным образом. При возникновении ложных срабатываний в приложении рекомендуется добавить дополнительный шаг помимо события Palm, чтобы вызвать меню руки, например полностью открытые пальцы.

**Е. не добавляйте кнопки рядом с кнопкой "наладонь (системная Главная)".** если кнопки меню руки расположены слишком близко к кнопке "Главная", они могут быть случайно активированы при взаимодействии с меню руки.

**Ж. тестирование, тестирование, тестирование:** у людей есть разные тексты с различными пороговыми значениями для удобства и дискомфорт и т. д. Не забудьте протестировать проект и получить отзывы от различных людей.

<br>

---

## <a name="hand-menu-placement-best-practices"></a>Рекомендации по размещению меню руки

В человеческих структурах улнар нервный — это нервный, которое работает вблизи кости улна. Улна — это длинная кость, найденная в фореарм, которая растягивается от уступа до самого маленького пальца.

Ниже приведено 2 рекомендуемых места на основе наших исследований:


:::row:::
    :::column:::
        ![расположение](images/UlnarSideHandMenu.gif) Улнар стороны<br>
        **A. Улнар внутри карманного компьютера**<br>
        Это надежное расположение, так как руки не пересекаются друг с другом. Это важно для точного обнаружения и отслеживания.
    :::column-end:::
    :::column:::
        ![расположение](images/UlnarAboveHandMenu.gif) Улнар стороны<br>
        **Б. Улнар**<br>
        Это расположение удобно для пользователей, так как им не нужно слишком много порождать ARM для взаимодействия с меню руки. Мы рекомендуем располагать меню, **13cm** над Palm, и выровняйте кнопки в улнар Palm. [Подробнее о оптимальном размере кнопки](interactable-object.md)<br>
        <br>
        По техническим соображениям мы рекомендуем использовать это расположение с одной требуемой реализацией: разработчику необходимо заморозить меню, когда пользователь, противоположный себе, получит решение о близком взаимодействии с ним. Это позволит избежать колебаний от перекрывающихся стрелок и позволяет быстрее ориентироваться на кнопки.<br>
        <br>
        Камеры HoloLens 2 точно определяют руки, если они отделены друг от друга. Любые перекрывающиеся руки могут привести к перемещению меню «рука» из расположения привязки.<br>
    :::column-end:::
:::row-end:::



<br>

---

## <a name="menu-positions-that-are-not-recommended"></a>Нерекомендуемые расположения меню
Мы выполнили исследование пользователей с помощью различных макетов и расположений в меню, поэтому **не рекомендуется использовать**следующие расположения, чтобы найти недостатки каждого исследования ниже:


:::row:::
    :::column:::
        ![](images/AboveArm.gif) ARM<br>
        **Над ARM**<br>
        1 — сложно сохранить хорошее отслеживание<br>
        2 — вызывает выносливости пользователя из-за неестественного расположения
    :::column-end:::
    :::column:::
        ![над пальцами](images/AboveFingers.gif)<br>
        **Над пальцами**<br>
        1-выносливости из-за длительного хранения<br>
        2 — проблемы с отслеживанием индекса и средних пальцев
    :::column-end:::
:::row-end:::

<br>

:::row:::
    :::column:::
        ![выше](images/handCenter.gif) Center Palm<br>
        **Выше-Center Palm**<br>
        1\. проблемы с отслеживанием из-за перекрывающихся стрелок<br>
        2-выносливости, из-за длительного времени для взаимодействия с меню
    :::column-end:::
    :::column:::
        ![сверху под рукой](images/TopFingerTip.gif) в **верхней части экрана**<br>
        проблемы с отслеживанием 1<br>
        2-выносливости с удержанием руки над нормальным<br>
        3\. проблемы с нажатием кнопок с другими пальцами случайным образом из-за ограниченного интервала между пальцами
    :::column-end:::
:::row-end:::

<br>

:::row:::
    :::column:::
        ![обратно](images/BackOfTheArm.gif) ARM<br>
        **Задняя часть ARM**<br>
        1 — может вызвать неслучайно кнопку "домой"<br>
        2 — неестественное или удобное расположение
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

<br>

---

## <a name="hand-menu-in-mrtk-mixed-reality-toolkit-for-unity"></a>Меню руки в МРТК (набор средств для смешанной реальности) для Unity
**[Мртк](https://github.com/Microsoft/MixedRealityToolkit-Unity)** предоставляет сценарии и примеры сцен для меню руки. Сценарий Хандконстраинтпалмуп Solver позволяет легко подключать любые объекты к ним с помощью различных настраиваемых параметров.

* [Меню МРТК с Хандконстраинт и Хандконстраинтпалмуп](https://github.com/microsoft/MixedRealityToolkit-Unity/blob/mrtk_release/Documentation/README_Solver.md#hand-menu-with-handconstraint-and-handconstraintpalmup)


<br>

---


## <a name="see-also"></a>См. также:

* [Курсоры](cursors.md)
* [Телекинез](point-and-commit.md)
* [Кнопка](button.md)
* [Активный объект](interactable-object.md)
* [Ограничивающая рамка и панель приложения](app-bar-and-bounding-box.md)
* [Оперирование](direct-manipulation.md)
* [Меню руки](hand-menu.md)
* [Быстрое меню](near-menu.md)
* [Коллекция объектов](object-collection.md)
* [Голосовая команда](voice-input.md)
* [Клавиатура](keyboard.md)
* [Подсказка](tooltip.md)
* [Планшет](slate.md)
* [Ползунок](slider.md)
* [Шейдер](shader.md)
* [Биллбординг и закрепление элемента в пространстве](billboarding-and-tag-along.md)
* [Индикация хода выполнения](progress.md)
* [Притяжение к поверхности](surface-magnetism.md)
