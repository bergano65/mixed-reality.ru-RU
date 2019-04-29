---
title: Контроллеры движения
description: Сведения о контроллерах движения смешанной реальности.
author: wguyman
ms.author: wguyman
ms.date: 03/21/2018
ms.topic: article
keywords: контроллеры 6dof, движения
ms.openlocfilehash: b44964ab872bd080349ecf1b04b3f7082b521a24
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604963"
---
# <a name="motion-controllers"></a>Контроллеры движения

Контроллеры движения [стандартные оборудования](hardware-accessories.md) , позволяющие пользователям потребуется выполнить действия в смешанной реальности. Преимущество контроллеров движения по [жесты](gestures.md) является то, что контроллеры точное положение в пространстве, что позволяет детально взаимодействия, добавляя цифровые объекты. Для Windows Mixed Reality иммерсивную движения контроллеры являются основным способом, что пользователи вступят в действие в их мир.

![Контроллеры движения Windows Mixed Reality](images/winmr-ck-1080x1080-350px.jpg)


## <a name="device-support"></a>Поддержка устройств

<table>
<tr>
<th>Компонент</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens (1-го поколения)</a></th><th style="width:150px">HoloLens 2</th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">Иммерсивную</a></th>
</tr><tr>
<td> Контроллеры движения</td><td style="text-align: center;"></td><td style="text-align: center;"></td><td style="text-align: center;"> ✔️</td>
</tr>
</table>

## <a name="hardware-details"></a>Сведения об оборудовании

>[!VIDEO https://www.youtube.com/embed/1nlcdDNOdm8]

Контроллеры движения Windows Mixed Reality предлагать быстрые и точные отслеживания перемещения в вашей поле представления с помощью датчиков в иммерсивных гарнитура, то есть, нет необходимости устанавливать оборудования на стене в своем пространстве. Эти контроллеры движения будет предлагать простоты установки и переносимость как иммерсивную Windows смешанной реальности. Нашим партнерам по устройствам плана на рынок и Продажа эти контроллеры на полках розничной торговли — это праздников.

![Знакомство с вашего контроллера](images/controllerimage-750px.png)<br>
*Знакомство с вашего контроллера*

**Функции:**
* Оптические отслеживания
* триггер
* Кнопки захвата
* Джойстик
* Сенсорная панель

## <a name="setup"></a>Установка

### <a name="before-you-begin"></a>Перед началом работы

**Вам потребуется:**
* Набор из двух контроллеров движения.
* Четыре АА.
* ПК может Bluetooth 4.0.

**Проверять наличие обновлений Windows, Unity и драйвера**
* Посетите [установить средства](install-the-tools.md) предпочтительный версиях Windows, Unity, и так далее для смешанной реальности разработки.
* Убедитесь, что у вас есть самые актуальные [гарнитура и движения драйверы контроллера](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/mixed-reality-software).

### <a name="pairing-controllers"></a>Связывание контроллеров

Контроллеры движения могут быть привязаны с хост-компьютера с помощью параметров Windows, как и любые другие устройства Bluetooth.

1. Вставьте 2 АА резервного контроллера. Оставьте крышку батареи по.
2. Если вы используете внешний USB-адаптера Bluetooth вместо встроенных radio Bluetooth, просмотрите [Bluetooth рекомендации](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality#bluetooth-best-practices) прежде чем продолжить. Для рабочего стола с встроенной переключатель убедитесь, что антенну.
3. Откройте **параметры Windows** -> **устройств** -> **добавьте Bluetooth или другое устройство** -> **Bluetooth** и удалите все более ранние экземпляры «движения — прямо» и «Движения контроллер — влево». Кроме того, просмотрите другие категории "устройства" в нижней части списка.
4. Выберите **добавьте Bluetooth или другое устройство** и Опробуйте начиная для обнаружения устройств Bluetooth.
5. Нажмите и удерживайте кнопку Windows контроллера, чтобы снова включить контроллер, после его освобождения buzzes.
6. Нажмите и удерживайте кнопку связывания (вкладка в секции аккумулятора) до индикаторы начала пульсирующий.
7. Подождите «Движения controller - слева» или «Движения controller - вправо» для отображения в нижнюю часть списка. Выберите, чтобы пары. Контроллер будет «вибрация» один раз при подключении.

   ![Выберите контроллер движения к паре, в том случае, если несколько экземпляров выберите один из появление нижнюю часть списка](images/450px-bluetooth-add-a-device-300px.png)<br>
   *Выберите «Движения controller» к паре; Если имеется несколько экземпляров, выберите его из нижней части списка*
   
8. Вы увидите контроллера, которые отображаются в разделе в настройках Bluetooth **«Мыши, клавиатуры и пера» категория** как **подключено**. На этом этапе вы получаете обновления встроенного по — см. в разделе [разделу](motion-controllers.md#updating-controller-firmware).
9. Повторно подключите титульной батареи.
10. Повторите шаги 1 – 9 для второго контроллера.

После успешного сопряжение оба контроллера, ваши параметры должны выглядеть следующим образом в разделе **«Мыши, клавиатуры и пера» категория** 

   ![Контроллеры движения подключен](images/450px-motion-controller-connected-300px.png)<br>
   *Контроллеры движения подключен*

Если контроллеры будут отключены после связывания, их состояние будет отображаться как парой. Если контроллеры оставаться без возможности восстановления в разделе «Другие устройства» связывание категории возможно лишь частично завершена и вам необходимо выполнить повторно для получения функциональных контроллера.

### <a name="updating-controller-firmware"></a>Обновление встроенного ПО контроллера

* Если доступно новое встроенное ПО контроллера иммерсивных гарнитура, подключенном к ПК, встроенное по будет помещено в контроллерах движения автоматически в следующий раз, что индикаторы включены. Обновления встроенного ПО контроллера обозначаются шаблон illuminating квадрантов светодиодный Индикатор, в кругу и занять 1 – 2 минуты.
* После завершения обновления встроенного ПО контроллера перезагрузки и повторного подключения. Оба контроллера должны быть подключены теперь. 
    
    ![Контроллеры подключен](images/cyk-connected-300px.jpg)<br>
    *Контроллеры, подключенных в параметры Bluetooth*

* Проверьте работу контроллеров должным образом:
    1. Запустите **смешанной реальности портала** и введите дома реальности Mixed.
    2. Переместить контроллерах и убедитесь отслеживания кнопки тестирования и [teleportation](navigating-the-windows-mixed-reality-home.md#getting-around-your-home) работает. Если не сделать, затем изъятия и возврата [движения Устранение неполадок контроллера](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality#motion-controllers).

## <a name="gazing-and-pointing"></a>Gazing и выберите пункт

Смешанная реальность Windows поддерживает две модели ключа для взаимодействия с **помощи и зафиксируйте** и **точки и зафиксировать**:
* С помощью **помощи и зафиксируйте**, пользователи целевой объект с их [помощи](gaze.md) и затем выберите объектов с воздуха касании вручную, игровой, clicker или голоса.
* С помощью **точки и зафиксировать**, пользователь может стремиться контроллер указывает на возможность перемещения в целевой объект и затем выбрать объекты с триггером контроллера.

Приложения, на которые указывает с контроллерами движения поддержки следует также включить взаимодействие на основе взглядом, где это возможно, для предоставления пользователям выбором в том, что устройства, которые они используют ввода.

### <a name="managing-recoil-when-pointing"></a>Управление recoil, указывая

При использовании контроллеров движения для точки и фиксации, пользователи будут использовать контроллер выбирать и выполнять действия, потянув его триггер. Которые стремятся триггер борьбу пользователи могут перейти в надежде контроллера, более поздней версии, в конце их опрашивающего триггера, чем они предназначены.

Для управления такой recoil, которая может возникнуть, когда пользователи извлекают триггер, приложение можно привязать его определения Рэй значение триггера аналогового оси поднимается выше 0.0. Вы можете отреагировать с помощью этого определения Рэй несколько кадров позже значение триггера по достижении 1.0, до тех пор, пока окончательный press происходит за короткий период. При использовании более высокого уровня [составного жеста касания](gestures.md#composite-gestures), Windows будет управлять это предназначенные для записи Рэй и время ожидания для вас.

## <a name="grip-pose-vs-pointing-pose"></a>Поза захвата для изменения и указывающего поза

Windows Mixed Reality поддерживает движения контроллеров в различных форм-факторов, дизайна каждый контроллер, отличающихся по отношению между положение руки пользователя и натуральный «переслать» направление этого приложения следует использовать для команды при подготовке к просмотру контроллер.

Чтобы лучше представить эти контроллеры, существует два вида можно выяснить, для каждого источника взаимодействия создает **поза захвата для изменения** и **поза указатель**.

### <a name="grip-pose"></a>Поза захвата для изменения

**Поза захвата для изменения** представляет расположение руку, обнаруживаемые HoloLens или palm, удерживая контроллером движения.

На иммерсивную, поза захвата для изменения лучше всего подходит для подготовки к просмотру **руку пользователя** или **объект содержится в руки пользователя**, например помехой или оружия. Захват поза также используется, когда визуализация контроллером движения, как **отрисовываемые модели** предоставляемых по Windows для перемещения контроллер использует поза захвата для изменения в качестве его источника и центр вращения.

Захват поза определяется специально следующим образом:
* **Возьмитесь за позиции**: Palm центроида при удержании контроллер, естественно, корректируется, влево или вправо, чтобы центрировать позиция в пределах захвата. На контроллере Windows Mixed Reality движения этой позиции обычно выравнивает может воспользоваться кнопкой.
* **Возьмитесь за правой оси в ориентации**: При открытии полностью свои силы для формирования позу плоских 5 палец, луч, является нормальным для вашей palm (вперед от левой palm назад от правой palm)
* **Возьмитесь за ориентации на ось, направленная вперед**: При закрытии вашей руке частично (как будто держа контроллеру), луч, указывающий «forward» трубку, образованное пальцы отличных от бегунка.
* **Возьмитесь за ориентации элемента вверх оси**: Ось вверх, право и прямого определения содержится в разрешении.

### <a name="pointer-pose"></a>Указатель поза

**Поза указатель** представляет собой кончик контроллера, указывающего вперед.

Поза системных указатель лучше использовать для raycast, когда вы будете **Подготовка к просмотру самой модели контроллера**. При отрисовке другого виртуального объекта вместо контроллера, такие как виртуальные оружия, должна указывать с луч, наиболее удобный для этого виртуального объекта, например луч, проходит по barrel дулом заданное приложением модели. Так как пользователи смогут просматривать виртуальным объектом и не физический контроллер, указывает с виртуальный объект будет более естественным для тех, с помощью приложения.

## <a name="controller-tracking-state"></a>Состояние отслеживания контроллера

Например наушники контроллер движения Windows Mixed Reality не требует настройки внешних отслеживания датчиков. Вместо этого контроллеры отслеживаются датчики в гарнитуры, сам.

Если пользователь перемещает контроллеров из поля зрения гарнитуры, в большинстве случаев Windows будет продолжать infer позиций контроллера и предоставлять их в приложение. Когда контроллер потерял visual отслеживание достаточно, долго позиций контроллера приведет к удалению в положения приблизительное точность.

На этом этапе система будет текст с блокировкой на контроллере, чтобы пользователь, отслеживания положение пользователя по мере перемещения, во время по-прежнему предоставляя true ориентации контроллера с помощью датчиков его внутренней ориентации. Многие приложения, использующие контроллеры указывали на и активировать элементы пользовательского интерфейса можно работать в обычном режиме в точности приблизительных без каких-пользователя.

&nbsp;

>[!VIDEO https://www.youtube.com/embed/rkDpRllbLII]

### <a name="reasoning-about-tracking-state-explicitly"></a>Рассуждения о явно отслеживания состояния

Приложения, которые желают обрабатывать позиций, иначе, основываясь на отслеживание состояния может пойти дальше и проверить свойства в состояние контроллера, например SourceLossRisk и PositionAccuracy:

<table>
<tr>
<th> Отслеживание состояния </th><th> SourceLossRisk </th><th> PositionAccuracy </th><th> TryGetPosition</th>
</tr><tr>
<td> <b>Высокая точность</b> </td><td style="background-color: green; color: white"> &lt; 1.0 </td><td style="background-color: green; color: white"> Высокий </td><td style="background-color: green; color: white"> true</td>
</tr><tr>
<td> <b>Высокая точность (риску потери)</b> </td><td style="background-color: orange"> == 1.0 </td><td style="background-color: green; color: white"> Высокий </td><td style="background-color: green; color: white"> true</td>
</tr><tr>
<td> <b>Точность приблизительных</b> </td><td style="background-color: orange"> == 1.0 </td><td style="background-color: orange"> Приблизительна </td><td style="background-color: green; color: white"> true</td>
</tr><tr>
<td> <b>Позиция не</b> </td><td style="background-color: orange"> == 1.0 </td><td style="background-color: orange"> Приблизительна </td><td style="background-color: orange"> false</td>
</tr>
</table>



Эти состояния отслеживания контроллера движения, определяются следующим образом:
* **Высокая точность:** Когда движения контроллер находится в пределах гарнитура поле зрения, он предоставит обычно позиций, высокой точности, основываясь на visual отслеживания. Обратите внимание, что перемещение контроллера, сразу же оставляет поле зрения или закрывается сразу же датчиков Гарнитура (например, пользователей с другой стороны) продолжит возвращать создает высокой точности на короткое время, в зависимости от инерционного отслеживания контроллера сам.
* **Высокая точность (риску потери):** При перемещении контроллера движения за край поле зрения гарнитуры, гарнитура скоро будет может визуально отслеживать положение контроллера. Приложение знает, когда контроллер достиг эту FOV границу, достаточно **SourceLossRisk** достичь 1.0. На этом этапе приложение можно приостановить контроллера жесты, требующих устойчивый поток создает очень высокого качества.
* **Точность приблизительных:** Когда контроллер потерял visual отслеживание достаточно, долго позиций контроллера приведет к удалению в положения приблизительное точность. На этом этапе система будет текст с блокировкой на контроллере, чтобы пользователь, отслеживания положение пользователя по мере перемещения, во время по-прежнему предоставляя true ориентации контроллера с помощью датчиков его внутренней ориентации. Многие приложения, использующие контроллеры указывали на и активировать элементы пользовательского интерфейса может работать как обычный while в точности приблизительных без каких-пользователя. Приложений с помощью более дешевые требования к входным данным, можно находить спад из **высокой** точность до одной **приблизительно** точности, проверяя **PositionAccuracy** свойство, для Пример для предоставления пользователю более масштабны hitbox на целевые объекты вне экрана в течение этого времени.
* **Позиция не:** Пока контроллер может работать в точности приблизительных в течение длительного времени, иногда система знает, что даже позицию заблокирован для текста не имеет смысла в данный момент. Например контроллер, который просто был включен может никогда не наблюдались визуально или пользователь может поместить работу контроллера, который затем передается другим пользователем. В эти моменты времени, система не будет предоставлять любой позиции в приложение и **TryGetPosition** возвратит значение false.

## <a name="interactions-low-level-spatial-input"></a>Взаимодействия: Операции низкоуровневого ввода пространственных

Взаимодействия core в руки и контроллеры движения **выберите**, **меню**, **осознавать**, **сенсорной панели**,  **Джойстик**, и **Главная**.
* **Выберите** представляет собой основной взаимодействие для активации голограмма, состоящий из пресс следуют выпуска. Контроллеры движения выполнить нажатие выберите с помощью контроллера триггера. Другие способы выполнения Select при помощи голоса [голосовые команды](voice-input.md) «Select». Выберите же взаимодействия можно использовать в любое приложение. Можно рассматривать выберите вариант эквивалент мышь, универсальной действие, которое Узнайте один раз и затем применить для всех приложений.
* **Меню** представляет собой дополнительный взаимодействие для реагирования на объект, используемый для извлечения контекстное меню, или предпринять другое действие вторичной. С контроллерами движения, можно предпринять действие меню с помощью контроллера *меню* кнопки. (т. е. Кнопка со значком «меню», "гамбургер" его)
* **Возьмитесь** — как пользователи могут напрямую принимать меры для объектов при их наличии, управление ими. С контроллерами движения можно сделать действие коммерческих тайн, тесно сжатие в первый раз. Контроллер движения могут быть обнаружены приступим с помощью кнопки захвата, palm триггера или других датчика.
* **Сенсорной панели** позволяет пользователю настроить действие в двух направлениях вдоль области сенсорной панели контроллера движения, их выполнения, нажав кнопку вниз на сенсорной панели. Сенсорные панели предоставляют нажатом состоянии, изменять состояния и нормализованное координатами x и y. X и Y диапазон от -1 до 1 по всему спектру циклическая сенсорной панели с центром в (0, 0). Для X -1 — в левой части, а 1 — справа. Для Y -1 находится в конце, а 1 — в верхней части.
* **Джойстик** позволяет пользователю настроить действие в двух направлениях, переместив джойстик контроллером движения в пределах досягаемости циклическая их выполнения, щелкнув джойстик вниз. Thumbsticks также предоставляют нажатом состоянии и нормализовать координатами x и y. X и Y диапазон от -1 до 1 по всему спектру циклическая сенсорной панели с центром в (0, 0). Для X -1 — в левой части, а 1 — справа. Для Y -1 находится в конце, а 1 — в верхней части.
* **Главная** является специальных системных действием, которое используется, чтобы вернуться в меню "Пуск". Это похоже на нажатие клавиши Windows на клавиатуре или кнопку Xbox на контроллере Xbox. Главная можно перейти, нажав кнопку Windows на контроллере движения. Обратите внимание, что вы также всегда можете вернуться на начальном произнеся «Привет, Кортана, Go Home». Приложения не может реагировать специально домашней действия, как эти параметры обрабатываются системой.

## <a name="composite-gestures-high-level-spatial-input"></a>Составные жесты: Высокоуровневые пространственных входных данных

Оба [передать жесты](gestures.md) и контроллеры движения могут отслеживаться в долгосрочной перспективе для определения общего набора обобщенных  **[составные жесты](gestures.md#composite-gestures)**. Это позволяет приложению определить высокоуровневые **коснитесь**, **хранения**, **манипуляции** и **навигации** жесты, ли пользователи в итоге руки или контроллеров.

## <a name="rendering-the-motion-controller-model"></a>Подготовка к просмотру модели контроллера движения

**Контроллер трехмерных моделей** Windows делает доступными для приложения модель отрисовываемые каждого контроллера движения в данный момент активным в системе. Когда приложение динамически загружаться и сформулируйте, эти системные контроллера модели во время выполнения, можно убедитесь, что приложение является макеты прямую совместимость для всех последующих контроллера.

Эти модели отрисовываемые должны преобразовываться для просмотра в **поза захвата для изменения** контроллера, как точку отсчета модели выравнивается с этой точкой в реальном мире. При отрисовке моделей контроллера, вы затем можете raycast сцены из **поза указатель**, представляющий луча, вдоль которого пользователи естественным образом хотят точки, учитывая физического проектирования для этого контроллера.

Дополнительные сведения о том, как загрузить модели контроллера динамически в Unity, см. в разделе [визуализации модель контроллера движения в Unity](gestures-and-motion-controllers-in-unity.md#rendering-the-motion-controller-model-in-unity) раздел.

**Штриховой рисунок 2D контроллера** хотя мы советуем, подключите контроллер в приложении советы, а также команды сами модели контроллера в приложении, некоторым разработчикам может потребоваться использовать представления art двухмерной строка контроллеров движения в плоский «учебник» или «инструкции» ПОЛЬЗОВАТЕЛЬСКИЙ ИНТЕРФЕЙС. Для тех разработчиков мы внесли .png движения контроллера строки art файлы, доступные в обоих черного и белого ниже (правой кнопкой мыши для сохранения).

![Предварительный просмотр движения контроллеры штриховой рисунок](images/motioncontrollers-black-preview-300px.png)

 [Контроллеры высокого разрешения движения штриховой рисунок в '' "белый '"](images/motioncontrollers-white.png)
 
 [Контроллеры высокого разрешения движения штриховой рисунок в '' "черный '"](images/motioncontrollers-black.png)

## <a name="faq"></a>Вопросы и ответы

### <a name="can-i-pair-motion-controllers-to-multiple-pcs"></a>Можно ли пара motion контроллеров к нескольким ПК?

Движения поддержка связывания с одного ПК. Следуйте инструкциям на [движения контроллера](motion-controllers.md#setup) сопряжение контроллеров.

### <a name="how-do-i-update-motion-controller-firmware"></a>Как обновить встроенное ПО контроллера motion?

Встроенное ПО контроллера движения является частью драйвера гарнитуры и будет автоматически обновляться на подключение при необходимости. Обновление встроенного по обычно занимает 1 – 2 минут в зависимости от качества рекламу на радио и связи Bluetooth. В редких случаях обновления встроенного ПО контроллера может занять до 10 минут, которые могут означать проблемами связи Bluetooth или помехам. См. в разделе [Bluetooth рекомендации по руководству энтузиаст](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality#bluetooth-best-practices) для устранения проблем с подключением. После обновления встроенного по будет контроллеры не выполнит перезагрузку и повторно подключиться к главным Компьютером (вы можете заметить индикаторы go ярко-для отслеживания). Если обновление встроенного по прерывается (например, контроллеры отключения электропитания), он будет предпринята попытка повторно при следующем запуске, питания контроллера.

### <a name="how-i-can-check-battery-level"></a>Как мне проверить уровень заряда батареи?

В [Windows Mixed Reality домашней](navigating-the-windows-mixed-reality-home.md), вы можете включить контроллере для просмотра его уровне заряда аккумулятора на обратной стороне виртуальная модель. Нет нет физического уровня индикатор батареи.

### <a name="can-you-use-these-controllers-without-a-headset-just-for-the-joysticktriggeretc-input"></a>Можно ли использовать эти контроллеры без гарнитуры? Только для ввода джойстика, триггер и т. д?

Не для универсальных Windows-приложений.

## <a name="troubleshooting"></a>Устранение неполадок

См. в разделе [движения Устранение неполадок контроллера](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/troubleshooting-windows-mixed-reality#motion-controllers) в руководству энтузиаст.

## <a name="filing-motion-controller-feedbackbugs"></a>Отправив движения контроллера обратной связи и ошибок

[Отзыв о нас](give-us-feedback.md) в центр отзывов с помощью категории «"Смешанной реальности->" ВВОД».

## <a name="see-also"></a>См. также
* [Жестов и контроллеры движения в Unity](gestures-and-motion-controllers-in-unity.md)
* [Взглядом, жесты и контроллеры движения в DirectX](gaze,-gestures,-and-motion-controllers-in-directx.md)
* [Жесты](gestures.md)
* [Входные данные MR 213: Контроллеры движения](mixed-reality-213.md)
* [Руководство по кого. В Windows Mixed Reality home](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/your-mixed-reality-home)
* [Руководство по кого. С помощью игры и приложения в Windows Mixed Reality](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/using-games-and-apps-in-windows-mixed-reality)
* [Как работает отслеживание поперек](https://docs.microsoft.com/windows/mixed-reality/enthusiast-guide/tracking-system)