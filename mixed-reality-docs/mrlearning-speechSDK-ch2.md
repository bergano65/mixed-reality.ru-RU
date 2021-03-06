---
title: Учебники по службам речи Azure — 2. Добавление автономного режима для локального перевода речи в текст
description: Пройдите этот курс, чтобы узнать, как реализовать пакет SDK для службы распознавания речи Azure в приложении смешанной реальности.
author: jessemcculloch
ms.author: jemccull
ms.date: 06/27/2019
ms.topic: article
keywords: mixed reality, unity, tutorial, hololens
ms.openlocfilehash: 962d7d4750cf59fe56de4af9088c90e8ecd0aa16
ms.sourcegitcommit: b6b76275fad90df6d9645dd2bc074b7b2168c7c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2019
ms.locfileid: "73913212"
---
# <a name="2-adding-an-offline-mode-for-local-speech-to-text-translation"></a>2. Добавление автономного режима для локального перевода речи в текст

В этом руководстве мы добавим автономный режим, который позволяет выполнять локальные преобразования речи в текст, когда не удается подключиться к службе Azure. Кроме того, мы будем *имитировать* отключенное состояние.

## <a name="instructions"></a>Инструкция

1. Выберите объект Lunarcom_Base в иерархии.

2. Нажмите кнопку Добавить компонент на панели инспектора. Найдите и выберите автономное распознавание Лунарком.

    ![Module4Chapter2step1im](images/module4chapter2step1im.PNG)

3. Щелкните раскрывающийся список в Лунаркомоффлинерекогнизер и выберите включено. Этот проект будет работать так же, как у пользователя нет подключения.

    ![Module4Chapter2step1im](images/module4chapter2step2im.PNG)

4. Нажмите кнопку Воспроизведение в редакторе Unity и проверьте его. Нажмите микрофон в левом нижнем углу сцены и начните говорить.

    >[!NOTE]
    >Так как мы отключены от сети, функции пробуждения слова недоступны. Вам нужно будет физически щелкать микрофон каждый раз, когда вы хотите, чтобы распознавание речи было признано в автономном режиме.

    Ниже приведен пример того, как может выглядеть сцена.

    ![Module4Chapter2exampleim](images/module4chapter2exampleim.PNG)

## <a name="congratulations"></a>Поздравляем!

Автономный режим включен. Теперь, когда вы работаете в автономном режиме, вы по-прежнему можете работать над проектом с помощью Speech-SDK!

[Следующее руководство: 3. Добавление компонента перевода речи Azure Cognitive Services](mrlearning-speechSDK-ch3.md)
