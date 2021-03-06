---
title: Учебники по пространственной привязке Azure — 1. Приступая к работе с пространственными привязками Azure
description: В рамках этого курса вы узнаете, как реализовать функцию распознавания лиц Azure в приложении смешанной реальности.
author: jessemcculloch
ms.author: jemccull
ms.date: 02/26/2019
ms.topic: article
keywords: mixed reality, unity, tutorial, hololens
ms.openlocfilehash: 0163b61bfbf8bd583532092581d94f63e1c2a624
ms.sourcegitcommit: bd536f4f99c71418b55c121b7ba19ecbaf6336bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77554683"
---
# <a name="1-getting-started-with-azure-spatial-anchors"></a>1. Приступая к работе с пространственными привязками Azure

## <a name="overview"></a>Обзор

Добро пожаловать на второй ряд учебников по HoloLens. В этой серии руководств из трех частей вы узнаете об основах использования пространственных привязок Azure.

В этом первом учебнике [Приступая к работе с пространственными привязками Azure](mrlearning-asa-ch1.md)вы узнаете о различных шагах, необходимых для запуска и завершения сеанса Azure, а также создания, отправки и скачивания привязок Azure на одном устройстве.

Во втором учебном курсе, [сохранении, извлечении и совместном использовании пространственных привязок Azure](mrlearning-asa-ch2.md)вы узнаете, как сохранять пространственные привязки Azure в нескольких сеансах приложения, сохраняя сведения о привязке в хранилище HoloLens 2 и совместное использование этих данных привязки с другими устройствами для выравнивания привязок на нескольких устройствах.

В третьем руководстве, в [котором отображается отзыв о пространственной привязке Azure](mrlearning-asa-ch3.md), вы узнаете, как предоставить пользователям Отзывы о событиях и состояниях привязки при использовании пространственных привязок Azure.

## <a name="objectives"></a>Задачи

* Изучите основы разработки с помощью пространственных привязок Azure для HoloLens 2
* Создание, передача и скачивание пространственных привязок

## <a name="prerequisites"></a>Предварительные требования

>[!TIP]
>Если вы еще не выполнили серию [учебников по началу работы](mrlearning-base.md) , рекомендуется сначала выполнить эти учебники.

* Компьютер с Windows 10, настроенный с требуемыми [установленными инструментами](install-the-tools.md).
* Пакет SDK для Windows 10 версии 10.0.18362.0 и выше.
* Базовые навыки программирования на C#.
* Устройство HoloLens 2, [настроенное для разработки](using-visual-studio.md#enabling-developer-mode).
* <a href="https://docs.unity3d.com/Manual/GettingStartedInstallingHub.html" target="_blank">Unity Hub</a> с Unity 2019.2.X и модулем поддержки сборки универсальной платформы Windows.
* Выполните инструкции из раздела [Создание ресурса пространственных привязок](https://docs.microsoft.com/azure/spatial-anchors/quickstarts/get-started-unity-hololens#create-a-spatial-anchors-resource) в разделе [Краткое руководство. Создание приложения Unity HoloLens, использующего учебник по пространственным привязок Azure](https://docs.microsoft.com/azure/spatial-anchors/quickstarts/get-started-unity-hololens) .

> [!IMPORTANT]
> Рекомендуемая версия Unity для этой серии руководств — Unity 2019.2.X. Это заменяет все требования к версии Unity и рекомендации, указанные выше.

## <a name="creating-the-unity-project"></a>Создание проекта Unity
<!-- TODO: Consider renaming to 'Creating and preparing the Unity scene and project'-->

В этом разделе вы создадите новый проект Unity и готовы подготовить его к разработке МРТК.

Для этого сначала выполните [инициализацию проекта и первого приложения](mrlearning-base-ch1.md), за исключением [сборки приложения в инструкции устройства](mrlearning-base-ch1.md#build-your-application-to-your-device) , которые включают следующие шаги:

1. [Создайте новый проект Unity](mrlearning-base-ch1.md#create-new-unity-project) и присвойте ему подходящее имя, например *учебники мртк*.

2. [Настройка проекта Unity для Windows Mixed Reality](mrlearning-base-ch1.md#configure-the-unity-project-for-windows-mixed-reality)

3. [Импорт необходимых ресурсов Текстмеш Pro](mrlearning-base-ch1.md#import-textmesh-pro-essential-resources)

4. [Импорт набора средств Mixed Reality](mrlearning-base-ch1.md#import-the-mixed-reality-toolkit)

5. [Настройка проекта Unity для набора средств Mixed Reality](mrlearning-base-ch1.md#configure-the-unity-project-for-the-mixed-reality-toolkit)

6. [Добавьте набор средств Mixed Reality к сцене Unity](mrlearning-base-ch1.md#configure-the-mixed-reality-toolkit) и присвойте сцене подходящее имя, например *азуреспатиаланчорс* .

Затем следуйте инструкциям в статье [Настройка профилей набора средств для смешанной реальности (изменение режима отображения пространственных сведений)](mrlearning-base-ch2.md#how-to-configure-the-mixed-reality-toolkit-profiles-change-spatial-awareness-display-option) , чтобы изменить профиль конфигурации мртк для сцены на **DefaultHoloLens2ConfigurationProfile** и изменить параметры отображения для сетки пространственной информации на **перекрытия**.

> [!CAUTION]
> Как упоминалось в разделе [Настройка проекта Unity для инструкций по набору средств Mixed Reality](mrlearning-base-ch1.md#configure-the-unity-project-for-the-mixed-reality-toolkit) , связанных выше, настоятельно рекомендуется не включать MSBuild для Unity.

## <a name="adding-inbuilt-unity-packages"></a>Добавление встроенных пакетов Unity
<!-- TODO: Consider renaming to 'Installing AR Foundation' -->

В этом разделе будет выполнена установка встроенного пакета AR Foundation для Unity, так как он необходим для пакета SDK для пространственных привязок Azure, который будет импортирован в следующем разделе.

В меню Unity выберите пункт **окно** > **Диспетчер пакетов**:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section2-step1-1.png)

> [!NOTE]
> В списке появится пакет AR Foundation, который может занять несколько секунд.

В окне Диспетчер пакетов выберите **AR Foundation** и установите пакет, нажав кнопку **установить** .

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section2-step1-2.png)

## <a name="importing-the-tutorial-assets"></a>Импорт ресурсов учебника

Скачайте и **импортируйте** следующие пользовательские пакеты Unity **в том порядке, в котором они перечислены**:

* [Азуреспатиаланчорс. пакет unitypackage](https://github.com/Azure/azure-spatial-anchors-samples/releases/download/v2.1.1/AzureSpatialAnchors.unitypackage) (версия:/с)
* [МРТК. HoloLens2. Unity. Tutorials. Assets. GettingStarted. 2.3.0.2. пакет unitypackage](https://github.com/microsoft/MixedRealityLearning/releases/download/getting-started-v2.3.0.2/MRTK.HoloLens2.Unity.Tutorials.Assets.GettingStarted.2.3.0.2.unitypackage)
* [МРТК. HoloLens2. Unity. Tutorials. Assets. Азуреспатиаланчорс. 2.3.0.0. пакет unitypackage](https://github.com/microsoft/MixedRealityLearning/releases/download/azure-spatial-anchors-v2.3.0.0/MRTK.HoloLens2.Unity.Tutorials.Assets.AzureSpatialAnchors.2.3.0.0.unitypackage)

> [!TIP]
> Напоминание о том, как импортировать пользовательский пакет Unity, можно найти в разделе Импорт инструкций по [набору средств для смешанной реальности](mrlearning-base-ch1.md#import-the-mixed-reality-toolkit) .

После импорта ресурсов учебника окно проекта должно выглядеть следующим образом:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section3-step1-1.png)

## <a name="creating-and-preparing-the-scene"></a>Создание и подготовка сцены
<!-- TODO: Consider renaming to 'Preparing the scene' -->

В этом разделе вы будете подготавливаем сцену, добавив некоторые из учебника Prefabs.

В окне проекта перейдите к разделу **активы** > **мртк. Учебник. Азуреспатиаланчорс** > **Prefabs** папку. Удерживая нажатой клавишу CTRL, щелкните **буттонпарент**, **DebugWindow**, **инструкции**и **парентанчор** , чтобы выбрать четыре Prefabs:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section4-step1-1.png)

Выбрав четыре Prefabs, перетащите их в окно Иерархия, чтобы добавить их в сцену:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section4-step1-2.png)

Чтобы сосредоточиться на объектах в сцене, можно дважды щелкнуть объект Парентанчор, а затем немного увеличить его:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section4-step1-3.png)

> [!TIP]
> Если вы найдете крупные значки в сцене, например, большие значки «'T» отвлекается от значков, их можно скрыть, переключив <a href="https://docs.unity3d.com/2019.1/Documentation/Manual/GizmosMenu.html" target="_blank">приспособлений</a> в положение OFF.

## <a name="configuring-the-buttons-to-operate-the-scene"></a>Настройка кнопок для функционирования сцены

В этом разделе вы добавите скрипты в сцену, чтобы создать ряд событий кнопок, демонстрирующих принципы поведения локальных и пространственных привязок Azure в приложении.

### <a name="1-configure-the-pressable-button-holo-lens-2-script-component"></a>1. Настройка нажатой кнопки Холо линза 2 (скрипт)

В окне Иерархия разверните объект **буттонпарент** и выберите первый дочерний объект с именем **стартазуресессион**:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section5-step1-1.png)

В окне инспектора выберите компонент **Холо линз 2 (скрипт)** , который можно нажать, и добавьте новый прослушиватель событий **нажатием кнопки ()** , щелкнув значок **+** :

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section5-step1-2.png)

Когда объект Стартазуресессион все еще выбран в окне Иерархия, щелкните и перетащите объект **парентанчор** из окна Иерархия в пустое поле **None (Object) (пустой объект)** только что добавленного прослушивателя событий, чтобы объект парентанчор прослушивает события нажатия кнопки.

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section5-step1-3.png)

Щелкните раскрывающийся список **без функций** того же прослушивателя событий, а затем выберите **анчормодулескрипт** > **стартазуресессион ()** , чтобы задать функцию стартазуресессион () в качестве действия, запускаемого при срабатывании события нажатия кнопки.

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section5-step1-4.png)

### <a name="2-configure-the-interactable-script-component"></a>2. Настройка компонента, поддерживающего взаимодействие (скрипт)

Если объект Стартазуресессион все еще выбран в окне "иерархия", в окне инспектора выберите компонент " **взаимодействие (скрипт)** " и повторите тот же процесс, что и в шаге 1 выше для события **OnClick ()** :

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section5-step2-1.png)

### <a name="3-configure-the-remaining-buttons"></a>3. Настройка оставшихся кнопок

Для каждой из оставшихся кнопок выполните процедуру, описанную в шагах 1 и 2, чтобы назначить функции для событий **нажатия кнопки ()** и **OnClick ()** .

* Для объекта **стопазуресессион** назначьте функцию Анчормодулескрипт > **стопазуресессион ()** .
* Для объекта **креатеазуреанчор** назначьте функцию Анчормодулескрипт > **креатеазуреанчор ()** ,
  * затем перетащите **парентанчор** в пустое поле **None (Game Object)** .
* Для объекта **ремовелокаланчор** назначьте функцию Анчормодулескрипт > **ремовелокаланчор ()** ,
  * затем перетащите **парентанчор** в пустое поле **None (Game Object)** .
* Для объекта **финдазуреанчор** назначьте функцию Анчормодулескрипт > **финдазуреанчор ()** .
* Для объекта **делетеазуреанчор** назначьте функцию Анчормодулескрипт > **делетеазуреанчор ()** .

### <a name="4-connect-the-scene-to-the-azure-resource"></a>4. Подключение сцены к ресурсу Azure

В окне «Иерархия» выберите объект **парентанчор** и в окне инспектора прокрутите вниз до компонента « **Диспетчер пространственных привязок» (script)** .

Затем в разделе **учетные данные** вставьте идентификатор и ключ учетной записи пространственной привязки, созданный в рамках [предварительных требований](mrlearning-asa-ch1.md#prerequisites)этого учебника, в соответствующие поля **идентификатор учетной записи пространственных** привязок и **ключ учетной записи пространственных привязок** .

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section5-step4-1.png)

## <a name="trying-the-basic-behaviors-of-azure-spatial-anchors"></a>Попытка базового поведения пространственных привязок Azure

Теперь, когда сцена настроена на демонстрацию основ пространственных привязок Azure, пора развернуть приложение, чтобы вы могли работать с пространственными привязками Azure.

### <a name="1-add-additional-required-capabilities"></a>1. Добавьте дополнительные необходимые возможности

В меню Unity выберите **изменить** > **Параметры проекта...** , чтобы открыть окно Параметры проигрывателя:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section6-step1-1.png)

В окне Параметры проигрывателя выберите **проигрыватель** , а затем **Параметры публикации**.

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section6-step1-2.png)

В разделе " **Параметры публикации**" прокрутите вниз до раздела " **возможности** " и дважды убедитесь, что возможности **InternetClient**, **Microphone**и **спатиалперцептион** , включенные при создании проекта в начале этого руководства, включены. Затем включите возможности **интернетклиентсервер**, **приватенетворкклиентсервер**, **ремоваблестораже**и веб- **камеры** :

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section6-step1-3.png)

### <a name="2-deploy-the-app-to-your-hololens-2"></a>2. Развертывание приложения в HoloLens 2

Пространственные привязки Azure не могут выполняться в Unity, поэтому для тестирования функциональности пространственных привязок Azure необходимо развернуть проект на устройстве.

> [!TIP]
> Напоминание о том, как создать и развернуть проект Unity в HoloLens 2, можно найти в руководстве по [сборке приложения на устройстве](mrlearning-base-ch1.md#build-your-application-to-your-device) .

### <a name="3-run-the-app-on-your-hololens-2-and-follow-the-in-app-instructions"></a>3. Запустите приложение в HoloLens 2 и следуйте инструкциям в приложении.

> [!CAUTION]
> Пространственные привязки Azure используют Интернет для сохранения и загрузки данных привязки, чтобы убедиться, что устройство подключено к Интернету.

Когда приложение запускается на устройстве, следуйте инструкциям на экране на панели инструкции учебника по пространственной точке управления Azure:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section6-step3-1.png)

## <a name="anchoring-an-experience"></a>Привязка интерфейса

В предыдущих разделах вы узнали основы пространственных привязок Azure. Мы использовали куб для представления и визуализации родительского объекта Game с присоединенной привязкой. В этом разделе вы узнаете, как закрепить весь интерфейс, поместив его в качестве дочернего элемента объекта Парентанчор.

### <a name="1-add-the-rocket-launcher-experience"></a>1. Добавьте интерфейс запуска Rocket

В окне проекта перейдите к **ресурсам** > **мртк. Учебник. GettingStarted** > **Prefabs** > **роккетлаунчер** папка и выберите **RocketLauncher_Complete** Prefab:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section7-step1-1.png)

Выбрав RocketLauncher_Complete prefab, перетащите его поверх объекта **парентанчор** в окне иерархии, чтобы сделать его дочерним элементом объекта парентанчор:

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section7-step1-2.png)

### <a name="2-reposition-the-rocket-launcher-experience"></a>2. изменение расположения процесса запуска Rocket

Размещение, поворот и масштабирование объекта **RocketLauncher_Complete** с учетом подходящего масштаба и ориентации, а также обеспечение того, что объект **парентанчор** по-прежнему предоставляется, например:

* **Координата Transform X** = 0, Y = 0, Z = 3,75
* **Поворот** преобразования X = 0, Y = 90, Z = 0
* Преобразование **масштаба** X = 10, Y = 10, Z = 10

![мрлеарнинг-ASA](images/mrlearning-asa/tutorial1-section7-step2-1.png)

В приложении пользователи теперь могут перемещать весь процесс запуска Rocket, перемещая куб.

> [!TIP]
> Существует множество потоков взаимодействия с пользователем для изменения положения, включая использование объекта изменения положения (например, Куба, используемого в этом руководстве), использование кнопки для переключения ограничивающего прямоугольника, окружающего интерфейс, использование положения и вращения. приспособлений и многое другое.

## <a name="congratulations"></a>Поздравляем!

В этом руководстве вы узнали основы пространственных привязок Azure. В руководстве предоставлено несколько кнопок, позволяющих изучить различные шаги, необходимые для запуска и завершения сеанса пространственных привязок Azure, а также для создания, отправки и скачивания пространственных привязок Azure на одном устройстве.

На следующем занятии вы узнаете, как сохранять идентификаторы привязки Azure в HoloLens 2 для получения, даже после перезапуска приложения, а также как передавать идентификаторы привязки между несколькими устройствами для достижения пространственного выравнивания.

[Следующее занятие: 2. сохранение, получение и совместное использование пространственных привязок Azure](mrlearning-asa-ch2.md)
