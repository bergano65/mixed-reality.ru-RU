---
title: Использование портала устройств Windows
description: Портал устройств Windows для HoloLens позволяет удаленно настраивать устройство и управлять им через Wi-Fi или USB. Портал устройств — это веб-сервер на вашем устройстве HoloLens, к которому можно подключаться из веб-браузера на ПК. Портал устройств содержит множество инструментов, которые помогут вам управлять HoloLens и отлаживать и оптимизировать приложения.
author: JonMLyons
ms.author: jlyons
ms.date: 02/24/2019
ms.topic: article
keywords: Портал устройств Windows, HoloLens
ms.openlocfilehash: 43ecfead7d2882d3624809bc05184f74131b8594
ms.sourcegitcommit: 1ec628a9107194c0a9d4073b5ca09ee816030e85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2020
ms.locfileid: "78202724"
---
# <a name="using-the-windows-device-portal"></a>Использование портала устройств Windows

<table>
<tr>
<th>Компонент</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens (1-го поколения)</a></th><th style="width:150px">HoloLens 2</th><th style="width:150px"><a href="immersive-headset-hardware-details.md">Иммерсивные гарнитуры</a></th>
</tr><tr>
<td> Портал устройств Windows</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"></td>
</tr>
</table>

Портал устройств Windows для HoloLens позволяет удаленно настраивать устройство и управлять им через Wi-Fi или USB. Портал устройств — это веб-сервер на вашем устройстве HoloLens, к которому можно подключаться из веб-браузера на ПК. Портал устройств содержит множество инструментов, которые помогут вам управлять HoloLens и отлаживать и оптимизировать приложения.

Эта документация связана с порталом устройств Windows для HoloLens. Сведения об использовании портала устройств Windows для рабочего стола (включая Windows Mixed Reality) см. в статье [Обзор портала устройств Windows](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal) .

## <a name="setting-up-hololens-to-use-windows-device-portal"></a>Настройка HoloLens для использования портала устройств Windows

1. Включите устройство HoloLens и наденьте его.
2. Выполните [жест запуска](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) для HoloLens2 или [раскрытия](https://docs.microsoft.com/hololens/hololens1-basic-usage#open-the-start-menu-with-bloom) в HoloLens (1-й общий), чтобы запустить главное меню. 
3. Взгляните на плитку **Параметры** и выполните жест [касания](https://docs.microsoft.com/hololens/hololens1-basic-usage#select-holograms-with-gaze-and-air-tap) в hololens (1-й общий) или выберите его в hololens 2, [касаясь его или используя руки](https://docs.microsoft.com/hololens/hololens2-basic-usage). 
4. Выберите пункт меню **Обновить**.
5. Выберите пункт меню **Для разработчиков**.
6. Включите **Режим разработчика**.
7. [Прокрутите вниз](gaze-and-commit.md#composite-gestures) и включите **портал устройств**.
8. Если вы настраиваете портал устройств Windows, чтобы вы могли развертывать приложения для этого HoloLens по USB или Wi-Fi, щелкните **пару** , чтобы [создать ПИН-код для пары](using-visual-studio.md). Пока вы не вводите ПИН-код в Visual Studio во время первого развертывания, оставьте приложение "Параметры" в всплывающем окне "закрепить".

   ![Включение режима разработчика в приложении "Параметры" для Windows holographic](images/deviceportalsettings.png)

## <a name="connecting-over-wi-fi"></a>Подключение через Wi-Fi

1. [Подключите HoloLens к Wi-Fi](connecting-to-wi-fi-on-hololens.md).
2. Найдите IP-адрес вашего устройства.
   * Найдите IP-адрес устройства в разделе **параметры > сеть & интернет > Wi-Fi > дополнительные параметры**.
3. В веб-браузере на компьютере перейдите по адресу https://< YOUR_HOLOLENS_IP_ADDRESS >
   * Браузер отобразит следующее сообщение: "возникла проблема с сертификатом безопасности этого веб-сайта". Это происходит потому, что сертификат, выданный Порталу устройства, является проверочным. Сейчас можно игнорировать эту ошибку сертификата и продолжить работу.

## <a name="connecting-over-usb"></a>Подключение по USB

1. [Установите средства](install-the-tools.md) , чтобы убедиться в наличии обновления 1 для Visual Studio с помощью средств разработчика Windows 10, установленных на компьютере. Это обеспечит подключение по USB.
2. Подключите HoloLens к компьютеру с помощью кабеля Micro-USB для HoloLens (1-го поколения) или USB-C для HoloLens 2.
3. В веб-браузере на компьютере перейдите по адресу [https://127.0.0.1:10080](https://127.0.0.1:10080).

## <a name="connecting-to-an-emulator"></a>Подключение к эмулятору

Можно также использовать Портал устройства вместе с эмулятором. Чтобы подключиться к порталу устройств, используйте [панель инструментов](using-the-hololens-emulator.md). Щелкните значок: ![открыть портал устройства](images/emulator-deviceportal.png) **открыть портал устройств**: откройте портал устройств Windows для ОС HoloLens в эмуляторе.

## <a name="creating-a-username-and-password"></a>Создание имени пользователя и пароля

![настроить доступ к](images/windows-device-portal-credentials-reset-page-1000px.png) портала устройств Windows<br>
*Настройка доступа к порталу устройств Windows*

При первом подключении к Порталу устройства на устройстве HoloLens необходимо создать имя пользователя и пароль.
1. В веб-браузере на компьютере введите IP-адрес HoloLens. Появится страница доступа «Настройка».
2. Щелкните **запрос ПИН-код** и просмотрите экран HoloLens, чтобы получить созданный ПИН-код.
3. Введите ПИН-код в поле ввода **ПИН-кода устройства** .
4. Введите имя пользователя, которое будет использоваться для подключению к Порталу устройства. Это не должно быть именем учетной записи Майкрософт (MSA) или доменным именем.
5. Введите пароль и подтвердите его. Длина пароля не должна быть менее 7 символов. Он может не соответствовать паролю учетной записи MSA или домена.софт или домена.
6. Щелкните **связать** , чтобы подключиться к порталу устройств Windows на HoloLens.

Если вы хотите изменить это имя пользователя или пароль в любое время, можно повторить эту процедуру, перейдя на страницу "безопасность устройства": https://< YOUR_HOLOLENS_IP_ADDRESS >/девицепаир.хтм.

## <a name="security-certificate"></a>Сертификат безопасности

Если в браузере отображается сообщение "Ошибка сертификата", его можно исправить, создав отношение доверия с устройством.

Каждое устройство HoloLens создает уникальный самозаверяющий сертификат для своего подключения SSL. По умолчанию веб-браузер на вашем ПК не доверяет этому сертификату, и вы можете получить «ошибку сертификата». Скачав этот сертификат с вашего устройства HoloLens (по USB или доверенной сети Wi-Fi) и настроив доверие к нему на своем ПК, можно безопасно подключаться к устройству.
1. **Убедитесь, что вы используете безопасную сеть (USB или сеть Wi-Fi, которой вы доверяете).**
2. Скачайте сертификат этого устройства со страницы "безопасность" на портале устройства.
   * Перейдите к: https://< YOUR_HOLOLENS_IP_ADDRESS >/девицепаир.хтм
   * Откройте узел для параметров системного >. 
   * Прокрутите вниз до пункта безопасность устройства, нажмите кнопку "скачать сертификат этого устройства".
3. Установите сертификат в хранилище "Доверенные корневые центры сертификации" на компьютере.
   * В меню Windows введите: Manage Computer Certificates (Управление сертификатами компьютеров) и запустите приложение.
   * Разверните папку **доверенный корневой центр сертификации** .
   * Щелкните папку **Сертификаты** .
   * В меню «Действие» выберите «Все задачи > Импорт...»
   * Выполните мастер импорта сертификатов, используя файл сертификата, загруженные с Портала устройств.
4. Перезапустите браузер.

>[!NOTE]
> Этот сертификат будет доверенным только для устройства, и пользователь должен будет снова пройти процесс, если устройство будет мигать.


## <a name="device-portal-pages"></a>Страницы Портала устройств

### <a name="home"></a>Главная

![Домашняя страница портала устройств Windows в Microsoft HoloLens](images/windows-device-portal-home-page-1000px.png)<br>
*Домашняя страница портала устройств Windows в Microsoft HoloLens*

Ваш сеанс на портале устройств начинается на Главной странице. Откройте другие страницы на панели навигации вдоль левого края главной страницы.

Панель инструментов в верхней части страницы предоставляет доступ к часто используемому состоянию и функциям.
* **Подключено**: указывает, подключено ли устройство к Wi-Fi.
* **Завершение работы**: отключает устройство.
* **Перезапуск**: выключает и включает питание на устройстве.
* **Безопасность**: открывает страницу «Безопасность устройства».
* **Холодный**: указывает температуру устройства.
* **A/C**: указывает, подключено ли устройство к источнику электропитания и заряжается ли оно.
* **Справка**: открывает страницу документации по интерфейсу REST.

На главной странице отображаются следующие сведения:
* **Состояние устройства:** отслеживает работоспособность устройства и сообщает о критических ошибках.
* **Сведения о Windows:** отображает имя HoloLens и текущую установленную версию Windows.
* Раздел **Настройки** содержит следующие параметры:
   * **IPD**: задает межзрачковое расстояние, то есть расстояние в миллиметрах между центрами зрачков смотрящего прямо пользователя. Этот параметр незамедлительно вступает в силу. Значение по умолчанию было вычислено автоматически при настройке устройства.
   * **Имя устройства**: присвойте имя устройству HoloLens. Необходимо перезапустить устройство после изменения этого параметра. После нажатия кнопки **сохранить**появится диалоговое окно с запросом о необходимости немедленной перезагрузки устройства или последующей перезагрузке.
   * **Параметры спящего режима**: определяют длительность времени ожидания перед переходом устройства в спящий режим при наличии питания от сети или при питании от аккумулятора.

### <a name="3d-view"></a>Трехмерное представление

![страница "объемное представление" на портале устройств Windows в Microsoft HoloLens](images/3dview-1000px.png)<br>
*страница «объемное представление» на портале устройств Windows в Microsoft HoloLens*

Используйте страницу «Трехмерное представление», чтобы оценить, как HoloLens воспринимает ваше окружение. В этом представлении можно перемещаться с помощью мыши:
* Поворот: щелчок левой кнопкой мыши + мышь;
* Сдвиг: щелчок правой кнопкой мыши + мышь;
* Масштаб: прокрутка мыши.
* **Параметры отслеживания**
   * Включите непрерывное Визуальное отслеживание, установив флажок **принудительное отслеживание визуальных**элементов. 
   * **Приостановка** останавливает отслеживание визуальных элементов.
* **Параметры просмотра**: Задайте параметры для трехмерного представления:
  * **Отслеживание**: указывает, активно ли отслеживание визуальных элементов.
  * **Показать пол**: отображает плоскость пола "в клеточку".
  * **Показать усеченную пирамиду**: отображение усеченной пирамиды представления.
  * **Показать плоскость стабилизации**: отображение плоскости, используемой HoloLens для стабилизации движения.
  * **Показать сетку**: отображает сетку пространственных сопоставлений, которая представляет вашу окружающую сеть.
  * **Показать пространственные привязки**: отображает пространственные привязки для активного приложения. Чтобы получить и обновить привязки, необходимо нажать кнопку Обновить.
  * **Показать детали**: отображение положения рук, кватернионов поворота головы, а также исходного вектора устройства по мере их изменения в режиме реального времени.
  * **Кнопка «Полный экран»** : отображает трехмерное представление в полноэкранном режиме. Нажмите клавишу ESC, чтобы выйти из полноэкранного режима.
* **Реконструкция поверхности**: нажмите кнопку **Обновить** , чтобы отобразить последнюю сетку пространственных сопоставлений с устройства. Выполнение полного прохода может занять некоторое время (до нескольких секунд). Сетка не обновляется автоматически в трехмерном представлении, поэтому необходимо вручную нажать кнопку **Обновить** , чтобы получить последнюю сеть с устройства. Нажмите кнопку **сохранить** , чтобы сохранить текущую сетку пространственных сопоставлений в качестве OBJ-файла на компьютере.
* **Пространственные привязки**: нажмите кнопку обновить, чтобы отобразить или обновить пространственные привязки для активного приложения.

### <a name="mixed-reality-capture"></a>Смешанный захват реальности

страница записи ![Mixed Reality на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-mixed-reality-capture-page-1000px.png)<br>
*Страница "запись смешанной реальности" на портале устройств Windows в Microsoft HoloLens*

Используйте страницу «Смешанный захват реальности», чтобы сохранить мультимедийные потоки для устройства HoloLens.
* **Параметры**. Управление захваченными потоками мультимедиа путем проверки следующих параметров:
  * **Голограммы**: захватывается holographic в потоке видео. Голограммы обрабатываются в режиме моно, а не стерео.
  * **Фото/видеокамера**: захват видеопотока с фото/видеокамеры.
  * **Звук микрофона**: захват звука с микрофона.
  * **Звук приложения**: захват звука из работающего в настоящее время приложения.
  * **Прорисовка с камеры**: позволяет расположить запись с точки зрения фотографии или видеокамеры, если [она поддерживается выполняющимся приложением](mixed-reality-capture-for-developers.md#render-from-the-pv-camera-opt-in) (только HoloLens 2).
  * **Качество предварительно просмотра в режиме реального времени**: выберите разрешение экрана, частоту кадров и скорость потока для предварительного просмотра в режиме реального времени.
* Нажмите кнопку **динамический просмотр** , чтобы отобразить поток записи. **Остановить динамический просмотр** останавливает поток отслеживания.
* Щелкните **запись** , чтобы начать запись потока смешанной реальности с использованием указанных параметров. **Прекращение записи** завершает запись и сохраняет ее.
* Щелкните " **принять фотографию** ", чтобы взять изображение из потока записи.
* **Видео и фотографии**: отображает список видео и фотографий, снятых на это устройство.

> [!NOTE]
> Существуют [ограничения на одновременную соблюдение требований](mixed-reality-capture-for-developers.md#simultaneous-mrc-limitations).
> * Если приложение пытается получить доступ к фото-и видеокамере на портале устройств Windows, запись видео будет прервана.
>   * HoloLens 2 не останавливает запись видео, если приложение обращается к фото-и видеокамере в режиме Шаредреадонли.
> * Если приложение активно использует фото-или видеокамеру, портал устройств Windows может получить фотографию или записать видео.
> * Потоковая трансляция:
>   * HoloLens (1-й общий) предотвращает доступ приложения к фото-и видеокамере во время потоковой передачи с портала устройств Windows.
>   * В случае, если приложение активно использует фотографию или видеокамеру, HoloLens (1-й общий) не сможет выполнить потоковую передачу.
>   * HoloLens 2 автоматически останавливает потоковую передачу в реальном времени, когда приложение пытается получить доступ к фото-или видеокамере в режиме Ексклусивеконтрол.
>   * HoloLens 2 может запустить поток в реальном времени, пока приложение активно использует камеру PV.

### <a name="performance-tracing"></a>Трассировка производительности

Страница "Трассировка производительности ![" на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-performance-tracing-page-1000px.png)<br>
*Страница "Трассировка производительности" на портале устройств Windows в Microsoft HoloLens*

Запишите трассировки [средства записи производительности Windows](https://msdn.microsoft.com/library/windows/hardware/hh448205.aspx) (ЗВЧ) из HoloLens.
* **Доступные профили**: выберите профиль WPR в раскрывающемся списке, затем щелкните или нажмите **Пуск** для запуска трассировки.
* **Пользовательские профили**: щелкните или нажмите **Обзор** для выбора профиля WPR на своем компьютере. Щелкните или нажмите **Передать и пуск** для запуска трассировки.

Чтобы отменить трассировку, щелкните ссылку "Закрыть". Оставайтесь на этой странице до завершения загрузки файла трассировки.

Захваченные файлы ETL можно открыть для анализа в [Windows Performance Analyzer](https://msdn.microsoft.com/library/windows/hardware/hh448170.aspx).

### <a name="processes"></a>Процессы

Страница "![процессов" на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-running-processes-page-1000px.png)<br>
*Страница "процессы" на портале устройств Windows в Microsoft HoloLens*

Отображаются сведения о выполняемых в настоящее время процессах. Сюда входят приложения и системные процессы.

### <a name="system-performance"></a>Производительность системы

![странице "производительность системы" на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-system-performance-page-1000px.png)<br>
*Страница "производительность системы" на портале устройств Windows в Microsoft HoloLens*

Отображение в реальном времени графиков системной диагностической информации, таких как использование питания, частота кадров и загрузка ЦП.

Ниже приведены доступные метрики:
* **Питание системы на кристалле**: мгновенная утилизация питания системы на кристалле: усредненное значение в течение одной минуты
* **Питание системы**: мгновенная утилизация питания системы: усредненное значение в течение одной минуты
* **Частота кадров**: кадры в секунду, пропущенные VBlanks в секунду и последующие пропущенные VBlanks
* **GPU**: использование модуля GPU, доступность в процентах от общего значения.
* **ЦП**: доступность в процентах от общего значения.
* **Ввод/вывод**: чтения и записи.
* **Сеть**: получение и отправка.
* **Память**: всего, используется, зафиксировано, Странично и не Странично

### <a name="apps"></a>Приложения

страница ![приложений на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-apps-page-1000px.png)<br>
*Страница "приложения" на портале устройств Windows в Microsoft HoloLens*

Управляет приложениями, установленными на HoloLens.
* **Установленные приложения**: удаление и запуск приложений.
* **Запущенные приложения**: отображаются все работающие в настоящее время приложения.
* **Установка приложения**: Выберите пакеты приложений для установки из папки на компьютере или в сети.
* **Зависимость**: добавление зависимостей для устанавливаемого приложения.
* **Развертывание**: Развертывание выбранного приложения и зависимостей в HoloLens.

### <a name="app-crash-dumps"></a>Аварийные дампы приложений

страница ![аварийных дампов приложений на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-dev-apps-crash-dumps-page-1000px.png)<br>
*Страница аварийного дампа приложения на портале устройств Windows в Microsoft HoloLens*

На этой странице можно собирать дампы сбоев для загрузки в сторонние приложения. Установите флажок **включить аварийные дампы** для каждого приложения, для которого требуется получить аварийные дампы. Вернитесь на эту страницу для сбора дампов сбоев. Файлы дампа можно [Открыть в Visual Studio для отладки](https://msdn.microsoft.com/library/d5zhxt22.aspx).

### <a name="file-explorer"></a>Проводник

![страница проводника на портале устройств Windows в Microsoft HoloLens](images/fileexplorer-1000px.png)<br>
*Страница проводника на портале устройств Windows в Microsoft HoloLens*

Используйте проводник для просмотра, отправки и скачивания файлов. Вы можете работать с файлами в папке "документы", в папке "рисунки" и в локальных папках хранилища для приложений, развернутых из Visual Studio или с помощью портала устройств.

### <a name="kiosk-mode"></a>Полноэкранный режим

>[!NOTE]
>Режим киоска доступен только в [коммерческом наборе Microsoft HoloLens](commercial-features.md).

Последние инструкции по включению режима киоска с помощью портала устройств Windows см. в статье [Настройка HoloLens в режиме киоска](https://docs.microsoft.com/hololens/hololens-kiosk#set-up-kiosk-mode-using-the-windows-device-portal-windows-10-version-1607-and-version-1803) в центре ИТ-специалистов Windows.

### <a name="logging"></a>Ведение журнала

Страница ведения журнала ![на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-logging-page-1000px.png)<br>
*Страница "ведение журнала" на портале устройств Windows в Microsoft HoloLens*

Управляет трассировкой событий реального времени для Windows (ETW) на HoloLens.

Установите флажок **Скрыть поставщики** , чтобы отображать только список **событий** .
* **Зарегистрированные поставщики**: выберите поставщика трассировки событий Windows и уровень трассировки. Уровень трассировки — это одно из следующих значений:
   1. ненормальный выход или прекращение;
   2. серьезные ошибки;
   3. Warnings
   4. предупреждения, не связанные с ошибками.

Щелкните или нажмите **Включить** для запуска трассировки. Поставщик добавляется в раскрывающийся список **Включенные поставщики**.
* **Пользовательские поставщики**: выбор пользовательского поставщика трассировки событий Windows и уровень трассировки. Определите поставщика по его GUID. Не включайте скобки в GUID.
* **Включенные поставщики**: приводится список включенных поставщиков. Выберите поставщика в раскрывающемся списке и щелкните или нажмите **Отключить**, чтобы остановить трассировки. Щелкните или нажмите **Стоп**, чтобы приостановить всю трассировку.
* **Журнал поставщиков**: отображаются поставщики трассировки событий Windows, которые были включены во время текущего сеанса. Щелкните или нажмите **Включить**, чтобы активировать поставщика, который ранее был отключен. Щелкните или нажмите **Очистить**, чтобы очистить журнал.
* **События**: список событий трассировки событий Windows выбранных поставщиков в формате таблицы. Эта таблица обновляется в режиме реального времени. Под этой таблицей нажмите кнопку **Очистить**, чтобы удалить из нее все события трассировки событий Windows. Это не приводит к отключению каких-либо поставщиков. Вы можете щелкнуть **Сохранить в файл**, чтобы экспортировать собранные события трассировки событий Windows локально в CSV-файл.
* **Фильтры**: позволяют ФИЛЬТРОВАТЬ события ETW, собираемые по идентификатору, ключевому слову, уровню, имени поставщика, имени задачи или тексту. Можно объединить несколько критериев вместе:
   1. Для критериев, применяемых к одному и тому же свойству, отображаются события, которые могут удовлетворять одному из этих критериев.
   2. Для критериев, применяемых к другому свойству, события должны удовлетворять всем критериям.

Например, можно указать критерий *(имя задачи содержит "foo" или "Bar") и (текст содержит "Error" или "warning")* .

### <a name="simulation"></a>Simulation

Страница "моделирование ![" на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-simulation-page-1000px.png)<br>
*Страница "моделирование" на портале устройств Windows в Microsoft HoloLens*

Позволяет записывать и воспроизводить входные данные для тестирования.
* **Комната захвата**: используется для загрузки файла моделирования комнаты, который содержит пространственную сетку сопоставления для окружения пользователя. Присвойте комнате имя, а затем нажмите кнопку **Capture (захват** ), чтобы сохранить данные в виде ксеф-файла на компьютере. Этот файл комнаты может быть загружен в эмулятор HoloLens.
* **Запись**. Проверьте потоки на запись, присвойте имя записи и щелкните **запись** , чтобы начать перекодирование. Выполните действия с HoloLens и нажмите кнопку " **Закрыть** ", чтобы сохранить данные в виде ксеф-файла на компьютере. Этот файл может быть загружен в эмулятор или на устройство HoloLens.
* **Воспроизведение**. Нажмите кнопку **отправить запись** , чтобы выбрать файл ксеф на компьютере и отправить данные в HoloLens.
* **Режим управления**: выберите **по умолчанию** или **моделирование** из раскрывающегося списка и нажмите кнопку " **задать** ", чтобы выбрать режим на HoloLens. Выбор «Симуляторы» отключает датчики на устройстве HoloLens и использует вместо них переданные смоделированные данные. Если переключиться на «Симуляторы», устройство HoloLens не будет реагировать на пользователя, пока не переключитесь обратно на значение «По умолчанию».

### <a name="networking"></a>Сеть

![страница "Сетевые подключения" на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-networking-page-1000px.png)<br>
*Страница "Сетевые подключения" на портале устройств Windows в Microsoft HoloLens*

Управляет подключениями Wi-Fi в HoloLens.
* **Адаптеры WiFi**: выберите адаптер Wi-Fi и профиль с помощью раскрывающихся элементов управления. Щелкните **Подключиться** , чтобы использовать выбранный адаптер.
* **Доступные сети**: список сетей Wi-Fi, к которым может подключаться HoloLens. Щелкните или коснитесь элемента **Обновить** , чтобы обновить список.
* **IP-конфигурация**: показывает IP-адрес и другие сведения о сетевом подключении.

### <a name="virtual-input"></a>Виртуальный ввод

![виртуальной страницы ввода на портале устройств Windows в Microsoft HoloLens](images/windows-device-portal-virtual-input-page-1000px.png)<br>
*Виртуальная страница ввода на портале устройств Windows в Microsoft HoloLens*

Отправляет клавиатурный ввод с удаленного компьютера на устройство HoloLens.

Щелкните или коснитесь региона в разделе **Виртуальная клавиатура** , чтобы разрешить отправку нажатий клавиш в HoloLens. Введите текст в текстовое поле **input Text (ввод текста** ) и нажмите кнопку **Отправить** , чтобы отправить нажатия клавиш в активное приложение.

## <a name="device-portal-rest-apis"></a>REST API портала устройств

Все на портале устройств основаны [REST API](device-portal-api-reference.md) , которые при необходимости можно использовать для программного доступа к данным и управления устройством.
