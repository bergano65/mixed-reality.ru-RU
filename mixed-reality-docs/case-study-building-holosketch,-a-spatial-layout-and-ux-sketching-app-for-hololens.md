---
title: Пример использования - HoloSketch стандартных, пространственных макет и UX, составляя эскиз приложения для HoloLens
description: HoloSketch предназначен для пространственных макета на устройстве и UX, составляя эскиз средство для HoloLens, помогающими заложить holographic опыт.
author: cre8ivepark
ms.author: dongpark
ms.date: 03/21/2018
ms.topic: article
keywords: HoloSketch, HoloLens, Windows Mixed Reality, составляя эскиз приложения
ms.openlocfilehash: d7f94a09bf4a8a16000c2345adf1a046dab4bd15
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600136"
---
# <a name="case-study---building-holosketch-a-spatial-layout-and-ux-sketching-app-for-hololens"></a>Пример использования - HoloSketch стандартных, пространственных макет и UX, составляя эскиз приложения для HoloLens

HoloSketch предназначен для пространственных макета на устройстве и UX, составляя эскиз средство для HoloLens, помогающими заложить holographic опыт. HoloSketch работает с помощью парных Bluetooth клавиатуры и мыши, а также жестов и голосовых команд. HoloSketch предназначена для обеспечения простого средства макета UX быструю визуализацию и итерации.

![HoloSketch: Пространственные макета и UX, составляя эскиз приложения для HoloLens.](images/holosketch-image-01-640px.png)<br>
*HoloSketch: Пространственные макет и UX, составляя эскиз приложения для HoloLens*

![Простое средство макета UX для быструю визуализацию и итерации.](images/holosketch-image-02.png)<br>
*Простое средство макета UX для быструю визуализацию и итерации*

## <a name="features"></a>Компоненты

### <a name="primitives-for-quick-studies-and-scale-prototyping"></a>Примитивы для быстрого внедрения и создания прототипов масштабирования

![С помощью простых фигур](images/holosketch-primitives-giphy.gif)

Простые фигуры можно используйте для быстрого внедрения massing и создания прототипов масштабирования.

### <a name="import-objects-through-onedrive"></a>Импорт объектов через OneDrive

![Импорт объектов](images/holosketch-importobjects-giphy.gif)

Импорт изображения PNG и JPG или трехмерные объекты FBX (требуется упаковки в Unity) в смешанной реальности посредством OneDrive.

### <a name="manipulate-objects"></a>Работать с объектами

![Обработка объектов](images/manipulate-objects-640px.jpg)

Работать с объектами (перемещения и поворота/масштаб) с интерфейсом знакомы трехмерного объекта.

### <a name="bluetooth-mousekeyboard-gestures-and-voice-commands"></a>Bluetooth, мыши или клавиатуры, жестов и голосовых команд

![поддерживает Bluetooth](images/supports-bluetooth-640px.jpg)

HoloSketch поддерживает мыши или клавиатуры Bluetooth, жестов и голосовых команд.

## <a name="background"></a>Фон

### <a name="importance-of-experiencing-your-design-in-the-device"></a>Важность возникновения данного дизайна, в устройстве

Если что-нибудь для HoloLens, очень важно для данного дизайна, в устройстве. Один из самых больших проблем в смешанной реальности проектирование приложений — это трудно получить представление о масштабирования, положение и глубина, особенно через традиционный 2D чертежей.

### <a name="cost-of-2d-based-communication"></a>Обмен данными по стоимости двумерные

Для эффективного взаимодействия потоки пользовательского интерфейса и сценариев для других пользователей, конструктор может оказаться тратит слишком много времени на создание ресурсов с помощью традиционных средств 2D, например Illustrator, Photoshop и PowerPoint. Таких 2D макетов часто требует дополнительных усилий, чтобы преобразовать их в 3D. Некоторые идеи, теряются при это преобразование из 2D в 3D.

### <a name="complex-deployment-process"></a>Процесс развертывания сложных

Так как смешанной реальности находится новый холст для нас, он включает в себя много итерации разработки и проб и ошибок по своей природе. Для конструктора, кто не знаком с инструментами, например Unity и Visual Studio не просто применить какое-то в HoloLens. Обычно необходимо пройти через процесс ниже, чтобы увидеть двухмерных и трехмерных графических объектов в устройство. Это было больших препятствием для конструкторов быстро итерации идеи и сценарии.

![Процесс развертывания сложных](images/holosketch-image-03-1000px.png)<br>
*Процесс развертывания*

### <a name="simplified-process-with-holosketch"></a>Упрощенный процесс с HoloSketch

С помощью HoloSketch мы хотели упростить этот процесс без привлечения средства разработки и портала связывание устройств. Использование OneDrive, пользователи могут легко помещать двухмерных и трехмерных ресурсов в HoloLens.

![Упрощенный процесс с HoloSketch](images/holosketch-image-04-1000px.png)<br>
*Упрощенный процесс с HoloSketch*

### <a name="encouraging-three-dimensional-design-thinking-and-solutions"></a>Поощряя трехмерного проектирования мышление и решения

Мы подумали, что это средство даст конструкторы возможность изучите решения в полностью трехмерном пространстве, а не зависнуть в 2D. Они не придется задумываться о создании 3D фона для их пользовательского интерфейса, так как фон является реального мира в случае Hololens. HoloSketch открывает позволяет разработчикам легко просматривать трехмерной графикой на устройство Hololens.

## <a name="get-started"></a>Начало работы

### <a name="how-to-import-2d-images-jpgpng-into-holosketch"></a>Как импортировать в HoloSketch двумерные изображения (JPG или PNG)

* Отправьте изображения JPG/PNG в папке OneDrive «Документы/HoloSketch».
* Из меню OneDrive в HoloSketch можно выбрать и поместить изображение в среде.

![Импорт изображения](images/import-2d-images-1000px.jpg)<br>
*Импорт изображений и трехмерных объектов через OneDrive*

### <a name="how-to-import-3d-objects-into-holosketch"></a>Импорт трехмерных объектов в HoloSketch

Перед отправкой в папке OneDrive, выполните следующие действия, чтобы упаковать трехмерных объектов в набор средств Unity. С помощью этого процесса можно импортировать файлы FBX/OBJ из Maya, кинотеатрах 4 D и Microsoft Paint 3D 3D программ.

>[!IMPORTANT]
>В настоящее время поддерживается создание пакета средств с 5.4.5f1 версии Unity.

1. Скачайте и откройте проект Unity [«AssetBunlder_Unity»](https://github.com/Microsoft/MRDesignLabs/tree/master/ReleasedApps/HoloSketch/AssetBundler_Unity). Этот проект Unity включает скрипт для средства формирования пакета.
2. Создайте новый объект GameObject.
3. Имя GameObject, на основе содержимого.
4. На панели Инспектора нажмите кнопку «Добавить компонент» и добавьте «Collider поле». 

   ![На панели Инспектора нажмите кнопку «Добавить компонент» и добавьте «Collider поле»](images/holosketch-10a-assetbundles-1000px.png)
   
   ![На панели Инспектора нажмите кнопку «Добавить компонент» и добавьте «Поле Collider» #2](images/holosketch-10b-assetbundles-1000px.png)

5. Импорт трехмерного FBX файла, перетащив его в панель «проект».
6. Перетащите объект на панели «иерархии» **в ваш новый объект GameObject**.

   ![Перетащите объект на панели иерархии под ваш новый объект GameObject](images/holosketch-12-assetbundles-1000px.png)

7. Настройте измерения collider, если он не совпадает с объектом. Повернуть объект сталкиваются **оси z**.

   ![Настройте collider измерения, если он не совпадает с объектом.](images/holosketch-13-assetbundles-1000px.png)

8. Перетащите объект из панели «иерархии» на панели «проект», чтобы **сделать prefab**.
9. В нижней части панели Инспектора откройте раскрывающийся список, создать и назначить новое уникальное имя. Ниже примере показано добавление и назначение «brownchair» для имени AssetBundle. 

   ![На нижней панели Инспектора откройте раскрывающийся список и назначить новое уникальное имя.](images/holosketch-14-assetbundles-1000px.png)

10. Подготовьте эскиз для объекта модели. 
   ![Перетащите изображения на панель «проект» и назначить имя, используемое для объекта.](images/holosketch-15-assetbundles-1000px.png)

11. Создайте папку с именем «Assetbundles», «Средства» в папке проекта Unity.

12. В меню ресурсов выберите «Создать AssetBundles», чтобы создать файл. 
   ![В меню ресурсов выберите «Создать AssetBundles», чтобы создать файл.](images/holosketch-15a-assetbundles.png)


13. **Отправьте созданный файл в папку /Files/Documents/HoloSketch в OneDrive.** Отправьте файл asset_unique_name только. Не нужно передать файлы манифеста или AssetBundles файл. <br>
![Добавление файлов в файлы/документы/HoloSketch/папку](images/holosketch-onedriveupload-1000px.png)
![вы увидите добавлены трехмерный объект, в меню HoloSketch в OneDrive](images/holosketch-14-onedriveexample-1000px.jpg)

## <a name="how-to-manipulate-the-objects"></a>Как работать с объектами

HoloSketch поддерживает традиционный интерфейс, который широко используется в трехмерных программного обеспечения. Вы можете использовать перемещение, поворот, масштабирование объектов с помощью жестов и мыши. Кроме того, можно быстро переключаться между различными режимами с помощью голоса или клавиатуры.

### <a name="object-manipulation-modes"></a>Режимы обработки объектов

![Как работать с объектами](images/holosketch-image-06-1000px.png)<br>
*Как работать с объектами*

### <a name="contextual-and-tool-belt-menus"></a>Меню контекстуальное и инструментарий

**С помощью контекстных меню**

Двойные жест касания, чтобы открыть контекстное меню. 

Элементы меню:
* **Область макета:** Это — это трехмерной сетки система, где вы можете макета несколько объектов и управлять ими как группой. Двойные air касание в области макета, чтобы добавить объекты к нему.
* **Примитивы:** Используйте кубы, сфер, цилиндров и конусы для massing внедрения.
* **OneDrive:** Откройте меню OneDrive для импорта объектов.
* **Справка:** Отображает справку экрана.

![Контекстные меню](images/holosketch-image-07.png)<br>
*Контекстные меню*

**С помощью меню средства лента**

Перемещение, поворот, масштабирование, сохранения и загрузки сцены меню будут доступны средства лента. 

## <a name="using-keyboard-gestures-and-voice-commands"></a>С помощью клавиатуры, жестов и голосовых команд

![Клавиатуры, жестов и голосовых команд](images/holosketch-image-08-1000px.png)<br>
*Клавиатуры, жестов и голосовых команд*

## <a name="download-the-app"></a>Загрузка приложения

<table style="border-collapse:collapse">
<tr>
<td style="border-style: none" width="60px"><img alt="HoloSketch app icon" width="60" height="60" src="images/holosketch-app-icon.png">
</td>
<td style="border-style: none"><a href="https://www.microsoft.com/store/p/holosketch/9p3br4t5m4tv">Загрузите и установите приложение HoloSketch бесплатно из Microsoft Store</a>
</td>
</tr>
</table>

## <a name="known-issues"></a>Известные проблемы
* В настоящее время создания пакета ресурса поддерживается с **5.4.5f1 версии Unity.**
* В зависимости от объема данных в OneDrive приложение может отображаться так, как если бы он был остановлен при загрузке содержимого OneDrive
* В настоящее время сохранения и загрузки функция поддерживает только простые объекты
* Текст, звук, видео и фотографий меню отключены в контекстные меню
* «Воспроизвести» в меню «инструментарий» удаляет элементы управления

## <a name="sharing-your-sketches"></a>Общий доступ к вашей чертежей

Можно использовать функцию записи видео в HoloLens, необходимо указать "Привет, Кортана, запуск и остановка записи". Нажмите клавишу тома вверх/вниз ключ друг с другом, чтобы сделать снимок вашего эскиза.

## <a name="about-the-authors"></a>Об авторах

<table style="border-collapse:collapse">
<tr>
<td style="border-style: none" width="60px"><img alt="Picture of Dong Yoon Park" width="60" height="60" src="images/dongyoonpark.jpg"></td>
<td style="border-style: none"><b>Park Yoon донг</b><br>Конструктор UX @Microsoft</td>
</tr>
<tr>
<td style="border-style: none" width="60px"><img alt="Picture of Patrick Sebring" width="60" height="60" src="images/paseb-60px.jpg"></td>
<td style="border-style: none"><b>Патрик Sebring</b><br>Разработчик @Microsoft</td>
</tr>
</table> 