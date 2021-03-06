---
title: Holographic кадров
description: Пользователи видят мир смешанной реальности через пакет Holographic.
author: cre8ivepark
ms.author: dongpark
ms.date: 03/21/2018
ms.topic: article
keywords: HoloLens, Windows Mixed Reality, holographic рамка, поле зрения
ms.openlocfilehash: 2145ba3b13bbd903299ad342292dfa8f5c05c023
ms.sourcegitcommit: 6bc6757b9b273a63f260f1716c944603dfa51151
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73434632"
---
# <a name="holographic-frame"></a>Holographic кадров

Пользователи видят мир смешанной реальности через прямоугольный экран гарнитуры. В HoloLens эта прямоугольная область называется голографическим экраном и позволяет пользователям видеть цифровое содержимое, наложенное на окружающий их мир. Проектирование опыта, оптимизированного для holographic кадров, создает возможности, устраняет проблемы и повышает удобство работы пользователей приложений смешанной реальности.

## <a name="designing-for-content"></a>Разработка для содержимого

Часто конструкторы, как правило, ограничивают область действия до того, что пользователь может сразу видеть, что позволяет добиться того, чтобы он полностью видел объект. Аналогично дизайнерам с сложными приложениями часто перегружаются с помощью содержимого, что приводит к чрезмерному взаимодействию пользователей с сложными взаимодействиями и неперегруженными интерфейсами. Конструкторы, создающие содержимое смешанной реальности, не должны ограничивать их работу непосредственно перед пользователем и в рамках их немедленного просмотра. Если физическое окружение пользователя сопоставлено, все эти поверхности должны рассматриваться как потенциальные холсты для цифрового содержимого и взаимодействия. Правильная структура взаимодействий и содержимого в интерфейсе должна порекомендовать пользователю перемещаться вокруг своего пространства, направлять внимание на ключевые материалы и видеть полный потенциал смешанной реальности.

Возможно, самый важный способ поощрение перемещения и исследования в приложении заключается в том, чтобы **позволить пользователям изменять работу**. Дайте пользователям короткий период времени "без задач" на устройстве. Это может быть так же просто, как размещение объекта в пространстве и предоставление пользователям возможности перемещаться по нему или заносить в комментарий Введение. Это время должно быть свободным от любых критических задач или специальных жестов (например, при касании воздуха), а значит, чтобы пользователи могли просматривать содержимое на устройстве, прежде чем требовать интерактивных действий или выполнения этапов приложения. Если это пользователь впервые с устройством, это особенно важно, так как он получит доступ к содержимому через holographic кадр и природу голограмм.

### <a name="large-objects"></a>Крупные объекты

Часто содержимое, которое вызывает интерфейс, особенно реальное содержимое, будет больше, чем Holographic. Объекты, которые обычно не могут помещаться в holographic, должны быть сжаты в соответствии с тем, как они впервые появились (в меньшем масштабе или на расстоянии). Ключ заключается в том, чтобы **позволить пользователям видеть полный размер объекта** до того, как масштабирование будет перегружать фрейм. Например, holographic-слон должен отображаться полностью в пределах фрейма, что позволяет пользователям формировать пространственное понимание общей фигуры животного, прежде чем изменять [масштаб в реальной](scale.md) форме рядом с пользователем.

С учетом полного размера объекта пользователи могут получить место, где нужно переместиться, и найти определенные части этого объекта. Аналогично, в опыт работы с увлекательным содержимым он может помочь в обращении к полному размеру этого содержимого. Например, если опыт проанализировать модель виртуального дома, он может помочь в уменьшении размера кукол-House, который пользователи могут активировать, чтобы понять, где они находятся внутри дома.

Пример разработки для больших объектов см. в разделе [компания Volvo автомобили](holographic-frame.md#volvo-cars).

### <a name="many-objects"></a>Множество объектов

В работе с множеством объектов или компонентов рекомендуется использовать все пространство вокруг пользователя, чтобы избежать загромождения непрямого кадра, непосредственно перед пользователем. Как правило, рекомендуется очень медленно представлять содержимое, и это особенно верно для тех, кто планирует обслуживать множество объектов для пользователя. Как и в случае с большими объектами, ключ заключается в том, чтобы **дать пользователям возможность понять структуру содержимого** в интерфейсе, помогая им получить пространственное представление о том, что именно по мере добавления содержимого в интерфейс.

Одним из способов добиться этого является предоставление постоянных точек (также известных как ориентиры) в интерфейсе, который привязывает содержимое к реальному миру. Например, ориентир может быть физическим объектом в реальной среде, например таблицей, в которой отображается цифровое содержимое, или цифровым объектом, например набором цифровых экранов, где часто отображается содержимое. Объекты также можно поместить в периферийное, чтобы дать пользователю возможность искать содержимое ключа, а обнаружение содержимого за пределами периферийное может быть автоматизировано [менеджерами](holographic-frame.md#attention-directors)по контролю внимания.

Размещение объектов в периферийное может дать пользователям возможность взглянуть на сторону, и это может быть автоматизировано менеджерами по контролю внимания, как описано ниже.

<br>

---

## <a name="user-comfort"></a>Комфорт пользователя

Для работы в смешанной реальности с большими объектами или многими объектами важно учитывать, сколько головного и горловинного перемещения необходимо для взаимодействия с содержимым. Опыт можно разделить на три категории с точки зрения головного перемещения: **горизонтальное** (боковое), **вертикальное** (вверх или вниз) или **иммерсивное** (по горизонтали и по вертикали). По возможности ограничьте большую часть взаимодействия с горизонтальной или вертикальной категориями, в идеале, с большинством действий, которые выполняются в центре holographic кадров, а заголовок пользователя находится в нейтральном положении. Избегайте взаимодействия, которые приводят к постоянному перемещению своего представления на неестественное положение головного элемента (например, всегда ищите доступ к взаимодействию с ключевым меню).

![оптимальный регион для содержимого — от 0 до 35 градусов ниже горизонта](images/optimal-field-of-view-2.png)<br>
*Оптимальный регион для содержимого — от 0 до 35 градусов ниже горизонта*

Горизонтальное перемещение по головному языку более [удобно](comfort.md) для частого взаимодействия, тогда как вертикальные перемещения должны быть зарезервированы для нестандартных событий. Например, опыт, включающий длинную горизонтальную временную шкалу, должен ограничивать вертикальное перемещение по головку для взаимодействия (например, поиск в меню).

Рассмотрите возможность стимулирования перемещения в полном тексте, а не только движения головок, помещая объекты вокруг пространства пользователя. Опыт перемещения объектов или больших объектов должен уделять особое внимание заголовку, особенно там, где они требуют частых перемещений по горизонтальной и вертикальной осям.

<br>

---

## <a name="interaction-considerations"></a>Вопросы взаимодействия

Как и в случае с содержимым, взаимодействие в режиме смешанной реальности не должно быть ограничено тем, что пользователь может сразу видеть. Взаимодействие может осуществляться в любом месте в реальной области вокруг пользователя, и эти взаимодействия могут помочь пользователям в изучении и исследовании возможностей.

### <a name="attention-directors"></a>Менеджеры по вопросам внимания

Указание интересующих точек или ключевых взаимодействий может быть важным для продвижения пользователей с помощью интерфейса. Пользовательское внимание и движение в holographic-кадре можно направлять с помощью тонких или высокопроизводительных способов. Не забывайте подключаться к директорам по контролю внимания с периодами бесплатного исследования в смешанной реальности (особенно в начале работы), чтобы не перегружать пользователя. В общем, существует два типа директоров по контролю внимания:
* **Визуальные директора:** Самый простой способ предоставить пользователю сведения о том, что следует перейти в конкретном направлении, — предоставить визуальную индикацию. Это можно сделать с помощью визуального эффект (например, путем, которым пользователь может визуально перейти к следующей части интерфейса) или даже как простые стрелки направления. Обратите внимание, что любой визуальный индикатор должен быть заземлен в среде пользователя, а не присоединен к пакету holographic или курсору.
* **Аудио директории.** [Пространственный звук](spatial-sound-design.md) может предоставить мощный способ установки объектов в сцене (предупреждения пользователей объектов, входящих в интерфейс) или обратить внимание на конкретную точку в пространстве (чтобы переместить представление пользователя на ключевые объекты). Использование аудио директоров для того, чтобы привлечь внимание пользователей, может быть более тонким и менее агрессивным, чем визуальные директора. В некоторых случаях лучше начать с аудио директор, а затем перейти к визуальному директорию, если пользователь не распознает подсказку. Аудио директоры также можно связать с визуальными директорами, чтобы добавить особое внимание.

### <a name="commanding-navigation-and-menus"></a>Командная страница, Навигация и меню

Интерфейсы в режиме смешанной реальности в идеале тесно связаны с цифровым содержимым, которым они управляют. Таким образом, плоские меню с произвольным плавающей запятой часто не идеально подходят для взаимодействия и могут быть сложными для удобства пользователей с помощью в holographic кадре. Для работы, которая требует таких элементов интерфейса, как меню или текстовые поля, рассмотрите возможность использования [метода с тегами](billboarding-and-tag-along.md) для отслеживания этого кадра после небольшой задержки. Избегайте блокировки содержимого в рамку, например отображение головного экрана, так как это может расположить пользователя и разобраться в восприятии других цифровых объектов в сцене.

Кроме того, рассмотрите возможность размещения элементов интерфейса непосредственно на конкретном содержимом, которое они управляют, что позволяет выполнять взаимодействие естественным образом относительно физического пространства пользователя. Например, разбейте сложное меню на отдельные части. С каждой кнопкой или группой элементов управления, прикрепленных к конкретному объекту, на который влияет взаимодействие. Чтобы использовать эту концепцию более подробно, рассмотрите возможность использования [взаимодействующих объектов](interactable-object.md).

### <a name="gaze-and-gaze-targeting"></a>Определение целевых объектов и взгляда

В holographic кадре представлен инструмент, позволяющий разработчикам запускать взаимодействия, а также оценивать, где двеллс внимание пользователя. [Взгляните](gaze-and-commit.md) на одно из [ключевых взаимодействий в HoloLens](interaction-fundamentals.md), где можно составлять пары с [жестами](gaze-and-commit.md#composite-gestures) (например, при касании воздуха) или [голоса](voice-input.md) (что позволяет более короткие и естественные взаимодействия на основе голоса). Таким образом, с помощью этого пакета holographic проявляется пространство для просмотра цифрового содержимого, а также взаимодействия с ним. Если в процессе взаимодействия с несколькими объектами в пространстве пользователя (например, множественное выделение объектов вокруг пространства пользователя с помощью команды «Взгляните + жест»), рассмотрите возможность переноса этих объектов в представление пользователя или ограничения необходимого заголовка. Перемещение, чтобы повысить [комфорт пользователя](comfort.md).

Кроме того, с помощью взгляда также можно следить за тем, какие объекты или части сцены пользователь расплачивает больше внимания. Это может быть особенно полезно для отладки, позволяя аналитическим средствам, таким как тепловые карты, видеть, где пользователи тратят больше всего времени или не имеют определенных объектов или взаимодействий. Отслеживание взгляда также может предоставить мощный инструмент для средств для начинающих (см. пример [кухни Лоу](holographic-frame.md#lowes-kitchen) ).

<br>

---

## <a name="performance"></a>Производительность

Правильное использование holographic-кадра является фундаментальным [показателем качества производительности](understanding-performance-for-mixed-reality.md) . Распространенная техническая и практическая задача — перегрузка пользовательского фрейма с цифровым содержимым, что приводит к ухудшению производительности визуализации. Вместо этого рекомендуется использовать все пространство вокруг пользователя для упорядочения цифрового содержимого с помощью описанных выше методик, чтобы уменьшить нагрузку на отрисовку и обеспечить оптимальное качество отображения.

Цифровое содержимое в holographic и более удачных кадрах HoloLens также можно связать с [плоскостью стабилизации](case-study-using-the-stabilization-plane-to-reduce-holographic-turbulence.md) для обеспечения оптимальной производительности и [стабильности](hologram-stability.md).

<br>

---

## <a name="examples"></a>Примеры.

### <a name="volvo-cars"></a>Компания Volvo автомобили

<iframe width="940" height="530" src="https://www.youtube.com/embed/DilzwF90vec" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

В шоврумной работе от компания Volvo автомобилей клиенты приглашаются о новых возможностях автомобилей в интерфейсе HoloLens, посвященном компания Volvo. Компания Volvo столкнулся с проблемой в holographic кадре: слишком большой автомобиль слишком велик для последующего размещения пользователя. Решением было начало работы с физическим ориентиром, Центральной таблицей в шоврум с небольшой цифровой моделью автомобиля, размещенной поверх таблицы. Это гарантирует, что пользователь видит полный автомобиль, когда он появился, позволяя понять понимание пространственного понимания по мере роста автомобиля до его реального масштаба в дальнейшем.

Опыт работы с компания Volvo также использует визуальных директоров, создавая длинный визуальный экран из модели небольших автомобилей в таблице на стене в комнате. Это приводит к эффекту "волшебного окна", в котором показано полное представление автомобиля на расстоянии, иллюстрирующие дополнительные возможности автомобиля в реальном масштабе. Головное перемещение является горизонтальным, без прямого взаимодействия с пользователем (вместо того, чтобы собирать подсказки визуально и из речевого сопровождения компания Volvo).

<br>

---

### <a name="lowes-kitchen"></a>Кухонный Лоу

Опыт магазина от Лоу приглашает клиентов в полноценную макетноеию кухни, чтобы продемонстрировать различные возможности ремоделирования, как видно через HoloLens. Кухни в магазине включает в себя физический задниок для цифровых объектов, пустой холст устройств, каунтертопс и ящиков для unfold.

Физические поверхности действуют как статические ориентиры, чтобы пользователь мог сами приступить к работе, так как Лоу связывает пользователя с помощью различных параметров продукта и завершается. Таким образом, связь может привлечь внимание пользователя к «холодильнику» или «центру кухни» для демонстрации цифрового содержимого.

![связи Лоу использует планшет, чтобы поработать с клиентами через интерфейс HoloLens.](images/loweskitchen-750px.jpg)<br>
*Связь Лоу использует планшет, чтобы помочь клиентам через интерфейс HoloLens.*

Взаимодействие с пользователем осуществляется по частям, с помощью интерфейса планшета, управляемого взаимосвязьм Лоу. В этом случае в качестве части роли связи можно было бы ограничить чрезмерное перемещение головного компьютера, чтобы привлечь внимание к интересующим вас точкам. Интерфейс планшета также обеспечивает связь лоу с данными взгляда в виде тепловой картыного представления кухни, помогая понять, где находится пользователь двеллинг (например, в определенной области ящика), чтобы точнее предоставить им руководство по реорганизации.

Более подробные сведения о Лоу кухни см. в [выступлении корпорации Майкрософт по Ignite 2016](https://www.youtube.com/watch?v=gC_4JxF0e_k).

<br>

---

### <a name="fragments"></a>Частей

В фрагментах HoloLens вы живете в монтажной сцене Virtual преступления, в которой отображаются подсказки и доказательства, а также Виртуальная комната для собраний, где вы говорите с символами, расположенными на стулах, и экономичными стенами.

![фрагменты были разработаны в домашней среде пользователя, с символами, взаимодействующими с реальными объектами и поверхностями.](images/fragments-750px.jpg)<br>
*Фрагменты были созданы в домашней среде пользователя, а символы взаимодействуют с реальными объектами и поверхностями.*

Когда пользователи изначально начинают работу, им предоставляется короткий период корректировки, где требуется очень небольшое взаимодействие, а не рекомендуется их искать. Это также помогает убедиться, что комната правильно сопоставлена с интерактивным содержимым игры.

На протяжении всего времени символы становятся фокальными точками и выступают в качестве визуальных директоров (перемещение головок между символами, переход на внешний вид или жест в отношении интересующих областей). Игра также полагается на более наглядные визуальные подсказки, когда пользователь занимает слишком много времени для поиска объекта или события и интенсивно использует Пространственный звук (особенно с голосовыми знаками при вводе сцены).

<br>

---

### <a name="destination-mars"></a>Назначение: режим MARS

В месте назначения: опыт работы в режиме MARS в [центре кеннединого пространства NASA](https://blogs.windows.com/devices/2016/09/19/hololens-experience-destination-mars-now-open-at-kennedy-space-center-visitor-complex/), посетители были приглашены на переход на рабочую область режима MARS, а также через виртуальное представление легендарном-космонавтам в путешествии Алдрин.

![виртуальный Алдрин станет фокальной точкой для пользователей в назначении: режим MARS.](images/destinationmars-750px.png)<br>
*Виртуальный разговор Алдрин станет фокальной точкой для пользователей в назначении: режим MARS.*

В качестве иммерсивного опыта эти пользователи должны были найти, переместив их заголовок во все направления, чтобы увидеть виртуальную Мартианную альбомную ориентацию. Хотя для того, чтобы обеспечить удобство работы пользователей, речевое сопровождение и виртуальное присутствие в Алдрине подают фокус на весь опыт. Эта виртуальная запись о разговоре (созданная в [смешанной реальности Microsoft Studios](https://www.microsoft.com/mixed-reality/capture-studios)) стояли в реальном времени, в углу комнаты, что позволяет пользователям видеть его в представлении почти полностью. Речевое сопровождение позволяет пользователям сосредоточиться на различных точках в окружении (например, набор Мартиан Rocks в пол или Mountain) с конкретными изменениями сцены или объектами, появившимися в нем.

![виртуальные экранные дикторы будут отслеживать движение пользователя, создавая мощную фокальную точку во время работы.](images/gazereset-750px.png)<br>
*Виртуальные экранные дикторы будут отслеживать движение пользователя, создавая мощную фокальную точку во всем опыте.*

Реалистичное представление о звуковых сигналах предоставляет эффективную фокальную точку, а также небольшие методы, позволяющие превратить пользователя в впечатление, если он там есть, и говорит. По мере того как пользователь перемещается по опыту, он переходит к пороговому значению перед возвратом в нейтральное состояние, если пользователь слишком далеко выходит за пределы периферийное. Если пользователь выйдет из программы передач полностью (например, чтобы взглянуть на что-нибудь в сцене), то вернемся к разговору. Такие приемы обеспечивают эффективное представление о возведении и создание фокальной точки в holographic кадре, уменьшая излишнее перемещение головного подразделения и повышая [комфортность пользователей](comfort.md).

## <a name="see-also"></a>См. также
* [Инстинктивное взаимодействие](interaction-fundamentals.md)
* [Комфорт](comfort.md)
* [Масштаб](scale.md)
* [Направление головы и остановка](gaze-and-dwell.md)
* [Стабильность голограммы](hologram-stability.md)
