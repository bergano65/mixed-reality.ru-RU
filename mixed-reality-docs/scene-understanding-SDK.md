---
title: Пакет SDK для понимания сцены
description: Инструкции по программированию для пакета SDK для сцены
author: szymons
ms.author: szymons
ms.date: 07/08/19
ms.topic: article
keywords: Основные сведения о сцене, пространственное сопоставление, Windows Mixed Reality, Unity
ms.openlocfilehash: 88138622987800ff86a24d05e1308e694e2dd2b1
ms.sourcegitcommit: c4c293971bb3205a82121bbfb40d1ac52b5cb38e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2019
ms.locfileid: "68941241"
---
## <a name="scene-understanding-sdk-overview"></a><span data-ttu-id="5a880-104">Общие сведения о пакете SDK для сцены</span><span class="sxs-lookup"><span data-stu-id="5a880-104">Scene Understanding SDK Overview</span></span>

<span data-ttu-id="5a880-105">Цель «понимание сцены» состоит в том, чтобы преобразовать неструктурированные данные датчика среды, записанные устройством смешанной реальности, и преобразовать их в эффективное, но абстрактное представление, которое интуитивно понятно и легко разрабатывается для.</span><span class="sxs-lookup"><span data-stu-id="5a880-105">The goal of Scene Understanding is to transform the un-structured environment sensor data that your Mixed Reality device captures and to convert it into a powerful but abstracted representation that is intuitive and easy to develop for.</span></span> <span data-ttu-id="5a880-106">Пакет SDK выступает в качестве коммуникационного уровня между приложением и сцены среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5a880-106">The SDK acts as the communication layer between your application and the Scene Understanding runtime.</span></span> <span data-ttu-id="5a880-107">Он предназначен для имитации существующих стандартных конструкций, таких как графики трехмерных сцен для трехмерных представлений и двумерных прямоугольников и панелей для двумерных приложений.</span><span class="sxs-lookup"><span data-stu-id="5a880-107">It's aimed to mimic existing standard constructs such as 3d scene graphs for 3d representations and 2D rectangles/panels for 2d applications.</span></span> <span data-ttu-id="5a880-108">Хотя сцены конструкций понимают, что имитирует сопоставление с конкретными платформами, которые можно использовать, в целом Сценеундерстандинг является независимым от платформы и обеспечивает взаимодействие между различными платформами, которые взаимодействуют с ним.</span><span class="sxs-lookup"><span data-stu-id="5a880-108">While the constructs Scene Understanding mimics will map to concrete frameworks you may use, in general SceneUnderstanding is framework agnostic allowing for interop between varied frameworks that interact with it.</span></span> <span data-ttu-id="5a880-109">По мере того, как в сцене понимается развитие роли пакета SDK, мы видим, что новые представления и возможности по-прежнему будут доступны в единой инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="5a880-109">As Scene Understanding evolves the role of the SDK is to ensure new representations and capabilities continue to be exposed within a unified framework.</span></span> <span data-ttu-id="5a880-110">В этом документе мы сперва предложим основные понятия, которые помогут вам ознакомиться с средой разработки и использованием, а затем предоставить более подробную документацию по конкретным классам и конструкциям.</span><span class="sxs-lookup"><span data-stu-id="5a880-110">In this document we will first introduce high level concepts that will help you get familiar with the development environment/usage and then provide more detailed documentation for specific classes and constructs.</span></span>

## <a name="where-do-i-get-the-sdk"></a><span data-ttu-id="5a880-111">Где получить пакет SDK?</span><span class="sxs-lookup"><span data-stu-id="5a880-111">Where do I get the SDK?</span></span>

<span data-ttu-id="5a880-112">Пакет SDK для Сценеундерстандинг загружается через NuGet.</span><span class="sxs-lookup"><span data-stu-id="5a880-112">The SceneUnderstanding SDK is downloadable via NuGet.</span></span>

[<span data-ttu-id="5a880-113">Пакет SDK для Сценеундерстандинг</span><span class="sxs-lookup"><span data-stu-id="5a880-113">SceneUnderstanding SDK</span></span>](https://www.nuget.org/packages/Microsoft.MixedReality.SceneUnderstanding/)

<span data-ttu-id="5a880-114">Прежде чем начать, обратите внимание, что пакет SDK выполняется поверх UWP и требует Windows SDK версии 18362 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="5a880-114">Before you begin please note that the SDK runs on top of the UWP, and requires Windows SDK version 18362 or higher.</span></span> 

### <a name="the-scene"></a><span data-ttu-id="5a880-115">Сцена</span><span class="sxs-lookup"><span data-stu-id="5a880-115">The Scene</span></span>

<span data-ttu-id="5a880-116">Устройство Mixed Reality постоянно интегрирует информацию о том, что она видит в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5a880-116">Your mixed reality device is constantly integrating information about what it sees in your environment.</span></span> <span data-ttu-id="5a880-117">При понимании сцены создаются все эти источники данных и создается одна единая абстракция.</span><span class="sxs-lookup"><span data-stu-id="5a880-117">Scene Understanding funnels all of these data sources and produces one single cohesive abstraction.</span></span> <span data-ttu-id="5a880-118">Понятие "сцена" создает сцены, представляющие собой композицию [сценеобжектс](scene-understanding-SDK.md#sceneobjects) , которая представляет экземпляр одной вещи (например, стены, потолка или этажа). Сами объекты сцены являются композицией [сценекомпонентс](scene-understanding-SDK.md#scenecomponents) , представляющей более детализированные элементы, составляющие этот сценеобжект.</span><span class="sxs-lookup"><span data-stu-id="5a880-118">Scene Understanding generates Scenes which are a composition of [SceneObjects](scene-understanding-SDK.md#sceneobjects) that represent an instance of a single thing, (e.g. a wall/ceiling/floor.) Scene Objects themselves are a composition of [SceneComponents](scene-understanding-SDK.md#scenecomponents) which represent more granular pieces that make up this SceneObject.</span></span> <span data-ttu-id="5a880-119">Примерами компонентов являются четыре и сетки, но в будущем они могут представлять ограничивающие рамки, конфликты мехсес, метаданные и т. д.</span><span class="sxs-lookup"><span data-stu-id="5a880-119">Examples of components are quads and meshes, but in the future could represent bounding boxes, collision mehses, metadata etc...</span></span>

<span data-ttu-id="5a880-120">Процесс преобразования необработанных данных датчика в сцену является потенциально дорогостоящей операцией, которая может занять секунды для средних пробелов (~ 10x10m) в минутах для очень больших пробелов (~ 50x50m) и, следовательно, не будет вычисляться устройством без запрос приложения.</span><span class="sxs-lookup"><span data-stu-id="5a880-120">The process of converting the raw sensor data into a Scene is a potentially expensive operation that could take seconds for medium spaces (~10x10m) to minutes for very large spaces (~50x50m) and therefore it is not something that is being computed by the device without application request.</span></span> <span data-ttu-id="5a880-121">Вместо этого создание сцены активируется вашим приложением по запросу.</span><span class="sxs-lookup"><span data-stu-id="5a880-121">Instead, Scene generation is triggered by your application on demand.</span></span> <span data-ttu-id="5a880-122">Класс Сценеобсервер содержит статические методы, которые могут вычислять или десериализовать сцену, которые затем можно перечислить или взаимодействовать с.</span><span class="sxs-lookup"><span data-stu-id="5a880-122">The SceneObserver class has static methods that can Compute or Deserialize a scene, which you can then enumerate/interact with.</span></span> <span data-ttu-id="5a880-123">Действие "вычисление" выполняется по требованию и выполняется в ЦП, но в отдельном процессе (драйвер Mixed Reality).</span><span class="sxs-lookup"><span data-stu-id="5a880-123">The "Compute" action is executed on-demand and executes on the CPU but in a seperate process (the Mixed Reality Driver).</span></span> <span data-ttu-id="5a880-124">Однако, пока мы выполняем вычисление в другом процессе, полученные данные сцены сохраняются и обслуживаются в приложении в объекте сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-124">However, while we do compute in another process the resulting Scene data is stored and maintained in your application in the Scene object.</span></span> 

<span data-ttu-id="5a880-125">Ниже приведена схема, на которой показан этот поток процесса, и приведены примеры двух приложений, взаимодействующих с сценой выполнения.</span><span class="sxs-lookup"><span data-stu-id="5a880-125">Below is a diagram that illustrates this process flow and shows examples of two applications interfacing with the Scene Understanding runtime.</span></span> 

![Схема процесса](images/SU-ProcessFlow.png)

<span data-ttu-id="5a880-127">В левой части находится схема среды выполнения Mixed Reality, которая всегда включена и выполняется в собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="5a880-127">On the left hand side is a diagram of the mixed reality runtime which is always on and running in its own process.</span></span> <span data-ttu-id="5a880-128">Эта среда выполнения отвечает за выполнение отслеживания устройств, а также воспроизводить и другие операции, которые помогут понять, что в мире используется для понимания и причины вокруг всего мира.</span><span class="sxs-lookup"><span data-stu-id="5a880-128">This runtime is responsible for performing device tracking, surface reconstruction, and other operations that Scene Understanding uses to understand and reason about the world around you.</span></span> <span data-ttu-id="5a880-129">В правой части схемы показаны два теоретических приложения, которые используют понимание сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-129">On the right side of the diagram, we show two theoretical applications that make use of Scene Understanding.</span></span> <span data-ttu-id="5a880-130">Первое приложение взаимодействует с МРТК, которое использует для внутренних целей пакет SDK, второе приложение выполняет вычисление и использует два экземпляра сепереате сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-130">The first application interfaces with MRTK which uses the Scene Understanding SDK internally, the second app computes and uses two sepereate scene instances.</span></span> <span data-ttu-id="5a880-131">Все три сцены на этой схеме создают отдельные экземпляры сцен, драйвер не отслеживает глобальное состояние, которое совместно используется приложениями, а объекты сцены в одной сцене не находятся в другой.</span><span class="sxs-lookup"><span data-stu-id="5a880-131">All 3 Scenes in this diagram generate distinct instances of the scenes, the driver is not tracking global state that is shared between applications and Scene Objects in one scene are not found in another.</span></span> <span data-ttu-id="5a880-132">Понимание сцены обеспечивает механизм отслеживания по времени, но это делается с помощью пакета SDK и кода. код, который выполняет это отслеживание, выполняется в пакете SDK в процессе приложения.</span><span class="sxs-lookup"><span data-stu-id="5a880-132">Scene Understanding does provide a mechanism to track over time, but this is done using the SDK and code the code that performs this tracking is running in the SDK in your app's process.</span></span>

<span data-ttu-id="5a880-133">Поскольку каждый монтажный кадр хранит данные в памяти приложения, можно предположить, что все функции объекта сцены или внутренние данные всегда выполняются в процессе приложения.</span><span class="sxs-lookup"><span data-stu-id="5a880-133">Because each Scene stores it's data in your application's memory space, you can assume that all function of the Scene object or it's internal data is always executed in your application's process.</span></span>

#### <a name="layout"></a><span data-ttu-id="5a880-134">Макет</span><span class="sxs-lookup"><span data-stu-id="5a880-134">Layout</span></span>

<span data-ttu-id="5a880-135">Чтобы работать с сценами, полезно знать и понять, как среда выполнения представляет компоненты логически и физически.</span><span class="sxs-lookup"><span data-stu-id="5a880-135">To work with Scene Understanding it may be valuable to know and understand how the runtime represents components logically and physically.</span></span> <span data-ttu-id="5a880-136">Сцена представляет данные с определенным макетом, который был выбран для простоты при сохранении базовой структуры, плиабле в соответствии с будущими требованиями, не требуя значительных изменений.</span><span class="sxs-lookup"><span data-stu-id="5a880-136">The Scene represents data with a specific layout that was chosen to be simple while maintaining an underlying structure that is pliable to meet future requirements without needing major revisions.</span></span> <span data-ttu-id="5a880-137">Сцена делает это, сохраняя все компоненты (стандартные блоки для всех объектов сцены) в плоском списке и определяя иерархию и композицию с помощью ссылок, где определенные компоненты ссылаются на другие.</span><span class="sxs-lookup"><span data-stu-id="5a880-137">The Scene does this by storing all Components (building blocks for all Scene Objects) in a flat list and defining hierarchy and composition through references where specific components reference others.</span></span>

<span data-ttu-id="5a880-138">Ниже представлен пример структуры как в плоской, так и в логической форме.</span><span class="sxs-lookup"><span data-stu-id="5a880-138">Below we present an example of a structure in both its flat and logical form.</span></span>

<table>
<tr><th><span data-ttu-id="5a880-139">Логический макет</span><span class="sxs-lookup"><span data-stu-id="5a880-139">Logical Layout</span></span></th><th><span data-ttu-id="5a880-140">Физический макет</span><span class="sxs-lookup"><span data-stu-id="5a880-140">Physical Layout</span></span></th></tr>
<tr>
<td>
<ul>
  <span data-ttu-id="5a880-141">Сцены</span><span class="sxs-lookup"><span data-stu-id="5a880-141">Scene</span></span>
  <ul>
  <li><span data-ttu-id="5a880-142">SceneObject_1</span><span class="sxs-lookup"><span data-stu-id="5a880-142">SceneObject_1</span></span>
    <ul>
      <li><span data-ttu-id="5a880-143">Mesh_1</span><span class="sxs-lookup"><span data-stu-id="5a880-143">Mesh_1</span></span></li>
      <li><span data-ttu-id="5a880-144">Quad_1</span><span class="sxs-lookup"><span data-stu-id="5a880-144">Quad_1</span></span></li>
      <li><span data-ttu-id="5a880-145">Quad_2</span><span class="sxs-lookup"><span data-stu-id="5a880-145">Quad_2</span></span></li>
    </ul>
  </li>
  <li><span data-ttu-id="5a880-146">SceneObject_2</span><span class="sxs-lookup"><span data-stu-id="5a880-146">SceneObject_2</span></span>
    <ul>
      <li><span data-ttu-id="5a880-147">Quad_1</span><span class="sxs-lookup"><span data-stu-id="5a880-147">Quad_1</span></span></li>
      <li><span data-ttu-id="5a880-148">Quad_3</span><span class="sxs-lookup"><span data-stu-id="5a880-148">Quad_3</span></span></li>
      </li></ul>
  </li>
  <li><span data-ttu-id="5a880-149">SceneObject_3</span><span class="sxs-lookup"><span data-stu-id="5a880-149">SceneObject_3</span></span>
    <ul>
      <li><span data-ttu-id="5a880-150">Mesh_3</span><span class="sxs-lookup"><span data-stu-id="5a880-150">Mesh_3</span></span></li>
    </ul>
  </ul>
</ul>
</td>
<td>
<ul>
  <li><span data-ttu-id="5a880-151">SceneObject_1</span><span class="sxs-lookup"><span data-stu-id="5a880-151">SceneObject_1</span></span></li>
  <li><span data-ttu-id="5a880-152">SceneObject_2</span><span class="sxs-lookup"><span data-stu-id="5a880-152">SceneObject_2</span></span></li>
  <li><span data-ttu-id="5a880-153">SceneObject_3</span><span class="sxs-lookup"><span data-stu-id="5a880-153">SceneObject_3</span></span></li>
  <li><span data-ttu-id="5a880-154">Quad_1</span><span class="sxs-lookup"><span data-stu-id="5a880-154">Quad_1</span></span></li>
  <li><span data-ttu-id="5a880-155">Quad_2</span><span class="sxs-lookup"><span data-stu-id="5a880-155">Quad_2</span></span></li>
  <li><span data-ttu-id="5a880-156">Quad_3</span><span class="sxs-lookup"><span data-stu-id="5a880-156">Quad_3</span></span></li>
  <li><span data-ttu-id="5a880-157">Mesh_1</span><span class="sxs-lookup"><span data-stu-id="5a880-157">Mesh_1</span></span></li>
  <li><span data-ttu-id="5a880-158">Mesh_2</span><span class="sxs-lookup"><span data-stu-id="5a880-158">Mesh_2</span></span></li>
</ul>
</td>
</tr>
</table>

<span data-ttu-id="5a880-159">На этом рисунке показана разница между физическим и логическим макетом сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-159">This illustration highlights the difference between the physical and logical layout of the Scene.</span></span> <span data-ttu-id="5a880-160">Справа мы видим иерархический макет данных, отображаемых приложением при перечислении сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-160">On the right we see the hierarchical layout of the data that your application sees when enumerating the scene.</span></span> <span data-ttu-id="5a880-161">Слева видно, что сцена на деле состоит из 12 отдельных компонентов, доступных по отдельности при необходимости.</span><span class="sxs-lookup"><span data-stu-id="5a880-161">On the left we see that the scene is actually comprised of 12 distinct components that are accessible individually if necessary.</span></span> <span data-ttu-id="5a880-162">При обработке новой сцены мы предполагаем, что приложения будут логически проходить эту иерархию, однако при отслеживании обновлений сцены некоторые приложения могут заинтересовать только те компоненты, которые являются общими для двух сцен.</span><span class="sxs-lookup"><span data-stu-id="5a880-162">When processing a new scene, we expect applications to walk this hierarchy logically, however when tracking between scene updates, some applications may only be interested in targeting specific components that are shared between two scenes.</span></span>

### <a name="high-level-overview"></a><span data-ttu-id="5a880-163">Общие сведения о высоком уровне</span><span class="sxs-lookup"><span data-stu-id="5a880-163">High-level Overview</span></span>

<span data-ttu-id="5a880-164">В следующем разделе представлен общий обзор конструкций в представлении сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-164">The following section provides a high-level overview of the constructs in Scene Understanding.</span></span> <span data-ttu-id="5a880-165">В этом разделе вы узнаете, как представлено представление сцены, а также о том, для чего используются различные компоненты.</span><span class="sxs-lookup"><span data-stu-id="5a880-165">Reading this section will give you an  understanding of how scenes are represented, and what the various components do/are used for.</span></span> <span data-ttu-id="5a880-166">В следующем разделе приводятся конкретные примеры кода и дополнительные сведения, которые будут включены в этот обзор.</span><span class="sxs-lookup"><span data-stu-id="5a880-166">The next section will provide concrete code examples and additional details that are glossed over in this overview.</span></span>

#### <a name="scenecomponents"></a><span data-ttu-id="5a880-167">сценекомпонентс</span><span class="sxs-lookup"><span data-stu-id="5a880-167">SceneComponents</span></span>

<span data-ttu-id="5a880-168">Теперь, когда вы понимаете логическую структуру сцен, теперь можно представить концепцию Сценекомпонентс и то, как они используются для создания иерархии.</span><span class="sxs-lookup"><span data-stu-id="5a880-168">Now that you understand the logical layout of scenes we can now present the concept of SceneComponents and how they are used to compose hierarchy.</span></span> <span data-ttu-id="5a880-169">Сценекомпонентс — это наиболее детализированные декомпозиции в Сценеундерстандинг, представляющие одну основную вещь, например сетку или четырехъядерный прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="5a880-169">SceneComponents are the most granular decompositions in SceneUnderstanding representing a single core thing, e.g. a mesh or a quad or a bounding box.</span></span> <span data-ttu-id="5a880-170">Сценекомпонентс — это вещи, которые могут обновляться независимо друг от друга и на которые могут ссылаться другие Сценекомпонентс, поэтому у них есть одно глобальное свойство с уникальным идентификатором, разрешающее этот тип механизма отслеживания и создания ссылок.</span><span class="sxs-lookup"><span data-stu-id="5a880-170">SceneComponents are things that can update independently and can be referenced by other SceneComponents, hence they have a single global property a unique Id, that allow for this type of tracking/referencing mechanism.</span></span> <span data-ttu-id="5a880-171">Идентификаторы используются для логической композиции иерархии сцены, а также для сохранения объектов (действия по обновлению одной сцены относительно другой).</span><span class="sxs-lookup"><span data-stu-id="5a880-171">Ids are used for the logical composition of scene hierarchy as well as object persistence (the act of updating one scene relative to another.)</span></span> 

<span data-ttu-id="5a880-172">Если все недавно вычисленные сцены обрабатываются как разные, и просто перечисление всех данных в нем, идентификаторы в значительной степени прозрачны.</span><span class="sxs-lookup"><span data-stu-id="5a880-172">If you are treating every newly computed scene as being distinct, and simply enumerating all data within it then Ids are largely transparent to you.</span></span> <span data-ttu-id="5a880-173">Однако если вы планируете отслеживание компонентов по нескольким обновлениям, вы будете использовать идентификаторы для индексирования и поиска Сценекомпонентс между объектами сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-173">However, if you are planning to track components over several updates you will use the Ids to index and find SceneComponents between Scene objects.</span></span>

#### <a name="sceneobjects"></a><span data-ttu-id="5a880-174">сценеобжектс</span><span class="sxs-lookup"><span data-stu-id="5a880-174">SceneObjects</span></span>

<span data-ttu-id="5a880-175">Сценеобжект — это Сценекомпонент, представляющий экземпляр "вещи", например стены, этаж, потолк и т. д. выражается по свойству Kind.</span><span class="sxs-lookup"><span data-stu-id="5a880-175">A SceneObject is a SceneComponent that represents an instance of a "thing" e.g. a wall, a floor, a ceiling, etc... expressed by their Kind property.</span></span> <span data-ttu-id="5a880-176">Сценеобжектс являются геометрическими и, следовательно, имеют функции и свойства, представляющие их расположение в пространстве, однако они не содержат геометрическую или логическую структуру.</span><span class="sxs-lookup"><span data-stu-id="5a880-176">SceneObjects are geometric, and therefore have functions and properties that represent their location in space, however they don't contain any geometric or logical structure.</span></span> <span data-ttu-id="5a880-177">Вместо этого Сценеобжектс ссылаться на другие Сценекомпонентс, в частности Сценекуадс и Сценемешес, которые предоставляют различные представления, поддерживаемые системой.</span><span class="sxs-lookup"><span data-stu-id="5a880-177">Instead, SceneObjects reference other SceneComponents, specifically SceneQuads and SceneMeshes which provide the varied representations that are supported by the system.</span></span> <span data-ttu-id="5a880-178">При вычислении новой сцены приложение, скорее всего, будет перечислять Сценеобжектс сцены, чтобы обработать его интерес.</span><span class="sxs-lookup"><span data-stu-id="5a880-178">When a new scene is computed, your application will most likely enumerate the Scene's SceneObjects to process what it's interested in.</span></span>

<span data-ttu-id="5a880-179">Сценеобжектс может иметь одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a880-179">SceneObjects can have any one of the following:</span></span>

<table>
<tr>
<th><span data-ttu-id="5a880-180">сценеобжекткинд</span><span class="sxs-lookup"><span data-stu-id="5a880-180">SceneObjectKind</span></span></th> <th><span data-ttu-id="5a880-181">Описание</span><span class="sxs-lookup"><span data-stu-id="5a880-181">Description</span></span></th>
</tr>
<tr><td><span data-ttu-id="5a880-182">Фон</span><span class="sxs-lookup"><span data-stu-id="5a880-182">Background</span></span></td><td><span data-ttu-id="5a880-183">Известно, что Сценеобжект <b>не</b> является одним из других распознаваемых видов объекта сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-183">The SceneObject is known to be <b>not</b> one of the other recognized kinds of scene object.</span></span> <span data-ttu-id="5a880-184">Этот класс не следует путать с неизвестным, где фон может не быть стенным, этажным, потолком и т. д. Хотя эта категория неизвестна, она еще не классифицирована.</span><span class="sxs-lookup"><span data-stu-id="5a880-184">This class should not be confused with Unknown where Background is known not to be wall/floor/ceiling etc... while unknown is not yet categorized.</span></span></b></td></tr>
<tr><td><span data-ttu-id="5a880-185">Брандмауэр</span><span class="sxs-lookup"><span data-stu-id="5a880-185">Wall</span></span></td><td><span data-ttu-id="5a880-186">Физическая стенка.</span><span class="sxs-lookup"><span data-stu-id="5a880-186">A physical wall.</span></span> <span data-ttu-id="5a880-187">Предполагается, что стены являются неперемещаемыми структурами окружающей среды.</span><span class="sxs-lookup"><span data-stu-id="5a880-187">Walls are assumed to be immovable environmental structures.</span></span></td></tr>
<tr><td><span data-ttu-id="5a880-188">Фабрич</span><span class="sxs-lookup"><span data-stu-id="5a880-188">Floor</span></span></td><td><span data-ttu-id="5a880-189">Полs — это любые поверхности, на которых может пройти один проход.</span><span class="sxs-lookup"><span data-stu-id="5a880-189">Floors are any surfaces on which one can walk.</span></span> <span data-ttu-id="5a880-190">Примечание. лестницы не являются этажами.</span><span class="sxs-lookup"><span data-stu-id="5a880-190">Note: stairs are not floors.</span></span> <span data-ttu-id="5a880-191">Кроме того, обратите внимание, что в этом этаже предполагается любая неанализируемойная поверхность и, следовательно, нет явного предположений в единственном этаже.</span><span class="sxs-lookup"><span data-stu-id="5a880-191">Also note, that floors assume any walkable surface and therefore there is no explicit assumption of a singular floor.</span></span> <span data-ttu-id="5a880-192">Многоуровневые структуры, пандуси и т. д. Все категории должны классифицироваться как пол.</span><span class="sxs-lookup"><span data-stu-id="5a880-192">Multi-level structures, ramps etc... should all classify as floor.</span></span></td></tr>
<tr><td><span data-ttu-id="5a880-193">Толок</span><span class="sxs-lookup"><span data-stu-id="5a880-193">Ceiling</span></span></td><td><span data-ttu-id="5a880-194">Верхняя поверхность комнаты.</span><span class="sxs-lookup"><span data-stu-id="5a880-194">The upper surface of a room.</span></span></td></tr>
<tr><td><span data-ttu-id="5a880-195">Платформа</span><span class="sxs-lookup"><span data-stu-id="5a880-195">Platform</span></span></td><td><span data-ttu-id="5a880-196">Крупная плоская поверхность, на которую можно поместить голограммы.</span><span class="sxs-lookup"><span data-stu-id="5a880-196">A large flat surface on which you could place holograms.</span></span> <span data-ttu-id="5a880-197">Они обычно представляют таблицы, каунтертопс и другие крупные горизонтальные поверхности.</span><span class="sxs-lookup"><span data-stu-id="5a880-197">These tend to represent tables, countertops and other large horizontal surfaces.</span></span></td></tr>
<tr><td><span data-ttu-id="5a880-198">World</span><span class="sxs-lookup"><span data-stu-id="5a880-198">World</span></span></td><td><span data-ttu-id="5a880-199">Зарезервированная метка для геометрических данных, не зависящая от меток.</span><span class="sxs-lookup"><span data-stu-id="5a880-199">A reserved label for geometric data that is agnostic to labeling.</span></span> <span data-ttu-id="5a880-200">Сетка, созданная путем установки флага обновления Енаблеворлдмеш, будет классифицироваться как мир.</span><span class="sxs-lookup"><span data-stu-id="5a880-200">The mesh generated by setting the EnableWorldMesh update flag would be classified as world.</span></span></td></tr>
<tr><td><span data-ttu-id="5a880-201">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="5a880-201">Unknown</span></span></td><td><span data-ttu-id="5a880-202">Этот объект сцены еще не классифицирован и ему назначен тип.</span><span class="sxs-lookup"><span data-stu-id="5a880-202">This scene object has yet to be classified and assigned a kind.</span></span> <span data-ttu-id="5a880-203">Это не следует путать с фоном, так как этот объект может быть любым, система просто не поступила с достаточной классификацией.</span><span class="sxs-lookup"><span data-stu-id="5a880-203">This should not be confused with Background, as this object could be anything, the system has just not come up with a strong enough classification for it yet.</span></span></td></tr>
</tr>
</table>

#### <a name="scenemesh"></a><span data-ttu-id="5a880-204">SceneMesh</span><span class="sxs-lookup"><span data-stu-id="5a880-204">SceneMesh</span></span>

<span data-ttu-id="5a880-205">Сценемеш — это Сценекомпонент, который приблизительно отражает геометрию произвольных геометрических объектов с помощью списка треугольников.</span><span class="sxs-lookup"><span data-stu-id="5a880-205">A SceneMesh is a SceneComponent that approximates the geometry of arbitrary geometric objects using a triangle list.</span></span> <span data-ttu-id="5a880-206">Сценемешес используются в нескольких разных контекстах, они могут представлять компоненты структуры ячеек ватертигхт или в виде Ворлдмеш, представляющего неограниченную реконструкции поверхности, связанную с сценой.</span><span class="sxs-lookup"><span data-stu-id="5a880-206">SceneMeshes are used in several different contexts, they can represent components of the watertight cell structure or as the WorldMesh which represents the unbounded Surface Reconstruction associated with the Scene.</span></span> <span data-ttu-id="5a880-207">Данные индекса и вершины, предоставляемые в каждой сетке, используют тот же привычный макет, что [и буферы вершин и индексов](https://msdn.microsoft.com/library/windows/desktop/bb147325%28v=vs.85%29.aspx) , которые используются для отрисовки сеток треугольников во всех современных API-интерфейсах отрисовки.</span><span class="sxs-lookup"><span data-stu-id="5a880-207">The index and vertex data provided with each mesh uses the same familiar layout as the [vertex and index buffers](https://msdn.microsoft.com/library/windows/desktop/bb147325%28v=vs.85%29.aspx) that are used for rendering triangle meshes in all modern rendering APIs.</span></span> <span data-ttu-id="5a880-208">Обратите внимание, что в сцене основные сведения об использовании сеток используют 32-разрядные индексы, и их необходимо разбить на фрагменты для определенных механизмов визуализации.</span><span class="sxs-lookup"><span data-stu-id="5a880-208">Note that in Scene Understanding, meshes use 32-bit indices and may need to be broken up into chunks for certain rendering engines.</span></span>

#### <a name="scenequad"></a><span data-ttu-id="5a880-209">сценекуад</span><span class="sxs-lookup"><span data-stu-id="5a880-209">SceneQuad</span></span>

<span data-ttu-id="5a880-210">Сценекуад — это Сценекомпонент, представляющий двумерные поверхности, занимающие трехмерный мир.</span><span class="sxs-lookup"><span data-stu-id="5a880-210">A SceneQuad is a SceneComponent that represents 2d surfaces that occupy the 3d world.</span></span> <span data-ttu-id="5a880-211">Сценекуадс можно использовать аналогично ARKit Арпланеанчор или Аркоре плоскости, но они предлагают более высокоуровневые функции, такие как двумерные холсты для использования в неструктурированных приложениях или дополненные UX.</span><span class="sxs-lookup"><span data-stu-id="5a880-211">SceneQuads can be used similarly to ARKit ARPlaneAnchor or ARCore Planes but they offer more high level functionality as 2d canvases to be used by flat apps, or augmented UX.</span></span> <span data-ttu-id="5a880-212">для четырех массивов предусмотрены двумерные API, которые делают размещение и разметку простыми в использовании, а разработка (за исключением отрисовки) с четырьмя областями должна быть более похожей на работу с плоскими холстами, чем с трехмерными сетками.</span><span class="sxs-lookup"><span data-stu-id="5a880-212">2D specific APIs are provided for quads that make placement and layout simple to use, and developing (with the exception of rendering) with quads should feel more akin to working with 2d canvases than 3d meshes.</span></span>

### <a name="scene-understanding-sdk-details-and-reference"></a><span data-ttu-id="5a880-213">Сцены сведения о пакете SDK и справочнике</span><span class="sxs-lookup"><span data-stu-id="5a880-213">Scene Understanding SDK Details and Reference</span></span>

#### <a name="sdk"></a><span data-ttu-id="5a880-214">SDK</span><span class="sxs-lookup"><span data-stu-id="5a880-214">SDK</span></span>

<span data-ttu-id="5a880-215">Следующий раздел поможет вам ознакомиться с основами Сценеундерстандинг.</span><span class="sxs-lookup"><span data-stu-id="5a880-215">The following section will help get you familiar with the basics of SceneUnderstanding.</span></span> <span data-ttu-id="5a880-216">В этом разделе приводятся основные сведения, в которых вы должны получить достаточно контекста для просмотра примеров приложений, чтобы увидеть, как Сценеундерстандинг используется глобально.</span><span class="sxs-lookup"><span data-stu-id="5a880-216">This section should provide you with the basics, at which point you should have enough context to browse through the sample applications to see how SceneUnderstanding is used holistically.</span></span>

#### <a name="initialization"></a><span data-ttu-id="5a880-217">Инициализация</span><span class="sxs-lookup"><span data-stu-id="5a880-217">Initialization</span></span>

<span data-ttu-id="5a880-218">Первым шагом для работы с Сценеундерстандинг является получение ссылки на объект сцены в приложении.</span><span class="sxs-lookup"><span data-stu-id="5a880-218">The first step to working with SceneUnderstanding is for your application to gain reference to a Scene object.</span></span> <span data-ttu-id="5a880-219">Это можно сделать одним из двух способов: сцена может вычисляться драйвером, или существующая сцена, которая была вычислена в прошлом, может быть десериализована.</span><span class="sxs-lookup"><span data-stu-id="5a880-219">This can be done in one of two ways, a Scene can either be computed by the driver, or an existing Scene that was computed in the past can be de-serialized.</span></span> <span data-ttu-id="5a880-220">Последнее особенно полезно для работы с Сценеундерстандинг во время разработки, где приложения и опыт можно быстро создавать прототипы без устройства смешанной реальности.</span><span class="sxs-lookup"><span data-stu-id="5a880-220">The latter is particularly useful for working with SceneUnderstanding during development, where applications and experiences can be prototyped quickly without a mixed reality device.</span></span>

<span data-ttu-id="5a880-221">Сцены вычисляются с помощью Сценеобсервер.</span><span class="sxs-lookup"><span data-stu-id="5a880-221">Scenes are computed using a SceneObserver.</span></span> <span data-ttu-id="5a880-222">Перед созданием сцены приложение должно запросить устройство, чтобы убедиться, что оно поддерживает Сценеундерстандинг, а также запросить доступ пользователей для получения информации, которая необходима Сценеундерстандинг.</span><span class="sxs-lookup"><span data-stu-id="5a880-222">Before creating a Scene, your application should query your device to ensure that it supports SceneUnderstanding, as well as to request user access for information that SceneUnderstanding needs.</span></span>

```cs
if (SceneObserver.IsSupported())
{
    // Handle the error
}

// This call should grant the access we need.
await SceneObserver.RequestAccessAsync();
```

<span data-ttu-id="5a880-223">Если не вызывается Рекуестакцессасинк (), то Вычисление новой сцены завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5a880-223">If RequestAccessAsync() is not called, computing a new Scene will fail.</span></span> <span data-ttu-id="5a880-224">Далее мы вычислим новую сцену, которая находится в корне вокруг гарнитуры смешанной реальности и имеет 10-м радиус.</span><span class="sxs-lookup"><span data-stu-id="5a880-224">Next we will compute a new scene that's rooted around the Mixed Reality headset and has a 10 meter radius.</span></span>

```cs
// Create Query settings for the scene update
SceneQuerySettings querySettings;

querySettings.EnableSceneObjectQuads = true;                                       // Requests that the scene updates quads.
querySettings.EnableSceneObjectMeshes = true;                                      // Requests that the scene updates watertight mesh data.
querySettings.EnableOnlyObservedSceneObjects = false;                              // Do not explicitly turn off quad inference.
querySettings.EnableWorldMesh = true;                                              // Requests a static version of the spatial mapping mesh.
querySettings.RequestedMeshLevelOfDetail = SceneMeshLevelOfDetail.Fine;            // Requests the finest LOD of the static spatial mapping mesh.

// Initialize a new Scene
Scene myScene = SceneObserver.Compute(querySettings, 10.0f);
```

#### <a name="initialization-from-data-aka-the-pc-path"></a><span data-ttu-id="5a880-225">Инициализация из данных (т. е.</span><span class="sxs-lookup"><span data-stu-id="5a880-225">Initialization from Data (aka.</span></span> <span data-ttu-id="5a880-226">Путь к компьютеру)</span><span class="sxs-lookup"><span data-stu-id="5a880-226">the PC Path)</span></span>

<span data-ttu-id="5a880-227">В то время как сцены можно вычислять для прямого потребления, их также можно вычислить в сериализованной форме для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="5a880-227">While Scenes can be computed for direct consumption, they can also be computed in serialized form for later use.</span></span> <span data-ttu-id="5a880-228">Это оказалось очень полезным для разработки, так как позволяет разработчикам работать и тестировать сцены без необходимости использования устройства.</span><span class="sxs-lookup"><span data-stu-id="5a880-228">This has proven to be very useful for development as it allows developers to work in and test Scene Understanding without the need for a device.</span></span> <span data-ttu-id="5a880-229">Процесс сериализации сцены практически идентичен его вычислению, поэтому данные возвращаются в приложение, а не десериализуется локально с помощью пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="5a880-229">The act of serializing a scene is nearly identical to computing it, the data is returned to your application instead of being deserialized locally by the SDK.</span></span> <span data-ttu-id="5a880-230">Вы можете выполнить десериализацию самостоятельно или сохранить его для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="5a880-230">You may then deserialize it yourself or save it for future use.</span></span>

```cs
// Create Query settings for the scene update
SceneUnderstanding.QuerySettings querySettings;

// Compute a scene but serialized as a byte array
byte[] newSceneBlob = SceneObserver.ComputeSerialized(querySettings, 10.0f);

// If we want to use it immediatley we can de-serialize the scene ourselves
Scene mySceneDeSerialized = Scene.Deserialize(newSceneBlob);

// Save newSceneBlob for later
```

#### <a name="sceneobject-enumeration"></a><span data-ttu-id="5a880-231">Перечисление Сценеобжект</span><span class="sxs-lookup"><span data-stu-id="5a880-231">SceneObject Enumeration</span></span>

<span data-ttu-id="5a880-232">Теперь, когда приложение содержит сцену, приложение будет искать и взаимодействовать с Сценеобжектс.</span><span class="sxs-lookup"><span data-stu-id="5a880-232">Now that your application has a scene, your application will be looking at and interacting with SceneObjects.</span></span> <span data-ttu-id="5a880-233">Это делается путем обращения к свойству **сценеобжектс** :</span><span class="sxs-lookup"><span data-stu-id="5a880-233">This is done by accessing the **SceneObjects** property:</span></span>

```cs
SceneObject firstFloor = null;

// Find the first floor object
foreach (var sceneObject in myScene.SceneObjects)
{
    if (sceneObject.Kind == SceneObjectKind.Floor)
    {
        firstFloor = sceneObject;
        break;
    }
}
```

#### <a name="component-update-and-re-finding-components"></a><span data-ttu-id="5a880-234">Обновление компонентов и их повторное обнаружение</span><span class="sxs-lookup"><span data-stu-id="5a880-234">Component update and re-finding components</span></span>

<span data-ttu-id="5a880-235">Существует другая функция, извлекающая компоненты в сцене с именем ***финдкомпонент***.</span><span class="sxs-lookup"><span data-stu-id="5a880-235">There is another function that retrieves components in the Scene called ***FindComponent***.</span></span> <span data-ttu-id="5a880-236">Эта функция полезна при обновлении объектов отслеживания и их поиске в последующих сценах.</span><span class="sxs-lookup"><span data-stu-id="5a880-236">This function is useful when updating tracking objects and finding them in subsequent scenes.</span></span> <span data-ttu-id="5a880-237">Следующий код вычислит новую сцену относительно предыдущей сцены, а затем найдет этаж в новой сцене.</span><span class="sxs-lookup"><span data-stu-id="5a880-237">The following code will compute a new scene relative to a previous scene and then find the floor in the new scene.</span></span>

```cs
// Compute a new scene, but tell the system that we want to compute relative to the previous scene
Scene myNextScene = SceneObserver.Compute(querySettings, 10.0f, myScene);

// Use the Id for the floor we found last time, and find it again
firstFloor = (SceneObject)myNextScene.FindComponent(firstFloor.Id);

if (firstFloor != null)
{
    // We found it again, we can now update the transforms of all objects we attatched to this floor transform
}
```

### <a name="accessing-meshes-and-quads-from-scene-objects"></a><span data-ttu-id="5a880-238">Доступ к сеткам и четырем из объектов сцены</span><span class="sxs-lookup"><span data-stu-id="5a880-238">Accessing Meshes and Quads from Scene Objects</span></span>

<span data-ttu-id="5a880-239">После обнаружения Сценеобжектс приложение, скорее всего, захочет получить доступ к данным, содержащимся в этих объемах.</span><span class="sxs-lookup"><span data-stu-id="5a880-239">Once SceneObjects have been found your application will most likely want to access the data that is contained n the quads/meshes that it is comprised of.</span></span> <span data-ttu-id="5a880-240">Доступ к этим данным осуществляется с помощью свойств « ***четыре*** » и « ***сетки*** ».</span><span class="sxs-lookup"><span data-stu-id="5a880-240">This data is accessed with the ***Quads*** and ***Meshes*** properties.</span></span> <span data-ttu-id="5a880-241">Следующий код будет перечислять все четыре и сетки нашего объекта Floor.</span><span class="sxs-lookup"><span data-stu-id="5a880-241">The following code will enumerate all quads and meshes of our floor object.</span></span>

```cs

// Get the matrix for the SceneObject
System.Numerics.Matrix4x4 floorTransform = firstFloor.LocationAsMatrix();

// Enumerate quads
foreach (var quad in firstFloor.Quads)
{
    // Process quads
}

// Enumerate meshes
foreach (var mesh in firstFloor.Meshes)
{
    // Process meshes
}
```

<span data-ttu-id="5a880-242">Обратите внимание, что это Сценеобжект, который имеет преобразование относительно начала сцены.</span><span class="sxs-lookup"><span data-stu-id="5a880-242">Notice that it is the SceneObject that has the transform that is relative to the Scene origin.</span></span> <span data-ttu-id="5a880-243">Это обусловлено тем, что Сценеобжект представляет экземпляр "вещь" и размещаемые в пространстве, а четыре части и сетки представляют геометрию, которая преобразуется относительно родительской.</span><span class="sxs-lookup"><span data-stu-id="5a880-243">This is because the SceneObject represents an instance of a "thing" and is locatable in space, the quads and meshes represent geometry that is transformed relative to their parent.</span></span> <span data-ttu-id="5a880-244">Можно использовать отдельный Сценеобжектс для ссылки на один и тот же Сценемеш или Сценекуад Сценекомпоневнтс. Кроме того, возможно, что у Сценеобжект есть более одного Сценемеш/Сценекуад.</span><span class="sxs-lookup"><span data-stu-id="5a880-244">It is possible for separate SceneObjects to reference the same SceneMesh/SceneQuad SceneComponewnts, and it is also possible that a SceneObject has more than one SceneMesh/SceneQuad.</span></span>

### <a name="dealing-with-transforms"></a><span data-ttu-id="5a880-245">Работа с преобразованиями</span><span class="sxs-lookup"><span data-stu-id="5a880-245">Dealing with Transforms</span></span>

<span data-ttu-id="5a880-246">Понимание сцены предоставило намеренную попытку выполнить согласование с традиционными представлениями трехмерной сцены при работе с преобразованиями.</span><span class="sxs-lookup"><span data-stu-id="5a880-246">Scene Understanding has made a deliberate attempt to align with traditional 3D scene representations when dealing with transforms.</span></span> <span data-ttu-id="5a880-247">Таким образом, каждая сцена ограничена одной системой координат, похожей на наиболее распространенные трехмерные представления среды.</span><span class="sxs-lookup"><span data-stu-id="5a880-247">Each Scene is therefore confined to a single coordinate system much like most common 3D environmental representations.</span></span> <span data-ttu-id="5a880-248">Если ваше приложение работает с монтажными кадрами, которые претягивают ограничение на один источник, можно привязать Сценеобжектс к Спатиаланчорс или создать несколько сцен и объединить их вместе, но для простоты предполагается, что ватертигхт сцены существуют самостоятельно. Источник, локализованный с помощью одного NodeId, определенного сценами:: Оригинспатиалграфнодеид.</span><span class="sxs-lookup"><span data-stu-id="5a880-248">If your application is dealing with Scenes that stretch the limit of what a single origin provides it can anchor SceneObjects to SpatialAnchors, or generate several scenes and merge them together, but for simplicity we assume that watertight scenes exist in their own origin that's localized by one NodeId defined by Scene::OriginSpatialGraphNodeId.</span></span>

<span data-ttu-id="5a880-249">В следующем примере кода Unity показано, как использовать восприятие Windows и API Unity для совмещения систем координат:</span><span class="sxs-lookup"><span data-stu-id="5a880-249">The following unity code, for example, shows how to use windows perception and Unity APIs to align coordinate systems together:</span></span>


```cs
    public static System.Numerics.Matrix4x4? GetSceneToUnityTransform(Guid nodeId)
    {
        System.Numerics.Matrix4x4? sceneToUnityTransform; 
       
        SpatialCoordinateSystem sceneSpatialCoordinateSystem = Windows.Perception.Spatial.Preview.SpatialGraphInteropPreview.CreateCoordinateSystemForNode(nodeId);
        SpatialCoordinateSystem unitySpatialCoordinateSystem = (SpatialCoordinateSystem)System.Runtime.InteropServices.Marshal.GetObjectForIUnknown(UnityEngine.XR.WSA.WorldManager.GetNativeISpatialCoordinateSystemPtr());

        sceneToUnityTransform = sceneSpatialCoordinateSystem.TryGetTransformTo(unitySpatialCoordinateSystem);

        if (sceneToUnityTransform != null)
        {
            sceneToUnityTransform = TransformUtils.ConvertRightHandedMatrix4x4ToLeftHanded(sceneToUnityTransform.Value);
        }
        
        return sceneToUnityTransform;
    }

    // Converts from right-handed to left handed coordinates
    public System.Numerics.Matrix4x4 ConvertRightHandedMatrix4x4ToLeftHanded(System.Numerics.Matrix4x4 transformationMatrix)
    {
        transformationMatrix.M13 = -transformationMatrix.M13;
        transformationMatrix.M23 = -transformationMatrix.M23;
        transformationMatrix.M43 = -transformationMatrix.M43;

        transformationMatrix.M31 = -transformationMatrix.M31;
        transformationMatrix.M32 = -transformationMatrix.M32;
        transformationMatrix.M34 = -transformationMatrix.M34;

        return transformationMatrix;
    }
```

<span data-ttu-id="5a880-250">И следующий код вызывает эту функцию:</span><span class="sxs-lookup"><span data-stu-id="5a880-250">And the following code calls this function:</span></span>

```cs
System.Numerics.Matrix4x4? sceneToUnityTransform = TransformUtils.GetSceneToUnityTransform(scene.OriginSpatialGraphNodeId);

// Set the root transform
Vector3 t;
Quaternion r;
Vector3 s;

System.Numerics.Matrix4x4.Decompose(sceneToUnityTransform, out s, out r, out t);
SceneRoot.Transform.SetPositionAndRotation(t, r);
```

### <a name="quad"></a><span data-ttu-id="5a880-251">Четырехъядерный</span><span class="sxs-lookup"><span data-stu-id="5a880-251">Quad</span></span>

<span data-ttu-id="5a880-252">Четыре из них были разработаны для упрощения сценариев размещения 2D-файлов и должны рассматриваться как расширения для элементов UX в двумерных холстах.</span><span class="sxs-lookup"><span data-stu-id="5a880-252">Quads were designed to facilitate 2D placement scenarios and should be thought of as extensions to 2D canvas UX elements.</span></span> <span data-ttu-id="5a880-253">Хотя четыре компонента являются компонентами Сценеобжектс и могут быть визуализированы в трехмерном виде, четыре интерфейса API предполагают, что четыре структуры являются 2D-структурами.</span><span class="sxs-lookup"><span data-stu-id="5a880-253">While Quads are components of SceneObjects and can be rendered in 3D, the Quad APIs themselves assume Quads are 2D structures.</span></span> <span data-ttu-id="5a880-254">Они предлагают такие сведения, как экстент, форма и предоставление API для размещения.</span><span class="sxs-lookup"><span data-stu-id="5a880-254">They offer information such as extent, shape, and provide APIs for placement.</span></span>

<span data-ttu-id="5a880-255">Четыре имеют прямоугольные экстенты, но они представляют собой произвольные геоповерхности.</span><span class="sxs-lookup"><span data-stu-id="5a880-255">Quads have rectangular extents, but they represent arbitrarily shaped 2d surfaces.</span></span> <span data-ttu-id="5a880-256">Чтобы включить размещение на этих 2D-поверхностях, взаимодействующих с четырьмя трехмерными средами, можно использовать служебные программы для обеспечения этого взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="5a880-256">To enable placement on these 2D surfaces that interact with the 3D environment quads offer utilities to make this interaction possible.</span></span> <span data-ttu-id="5a880-257">В настоящее время понятие сцены предоставляет две такие функции: **финдцентермостплацемент** и **жетокклусионмаск**.</span><span class="sxs-lookup"><span data-stu-id="5a880-257">Currently Scene Understanding provides two such functions, **FindCentermostPlacement** and **GetOcclusionMask**.</span></span> <span data-ttu-id="5a880-258">Финдцентермостплацемент — это интерфейс API высокого уровня, который определяет положение на самом большом месте, где может быть размещен объект, и пытается найти лучшее место для объекта, гарантируя, что ограничивающий прямоугольник будет находиться на базовой поверхности.</span><span class="sxs-lookup"><span data-stu-id="5a880-258">FindCentermostPlacement is a high level API that locates a position on the quad where an object can be placed and will try to find the best location for your object guaranteeing that the bounding box you provide will reside on the underlying surface.</span></span>

<span data-ttu-id="5a880-259">В следующем примере показано, как найти центермост место и привязать голограмму к четырем.</span><span class="sxs-lookup"><span data-stu-id="5a880-259">The following example shows how to find the centermost placeable location and anchor a hologram to the quad.</span></span>

```cs
// This code assumes you already have a "Root" object that attaches the Scene's Origin.

// Find the first quad
foreach (var sceneObject in myScene.SceneObjects)
{
    // Find a wall
    if (sceneObject.Kind == SceneObjectKind.Wall)
    {
        // Get the quad
        var quads = sceneObject.Quads;
        if (quads.Count > 0)
        {
            // Find a good location for a 1mx1m object  
            System.Numerics.Vector2 location;
            if (quads[0].FindCentermostPlacement(new System.Numerics.Vector2(1.0f, 1.0f), out location))
            {
                // We found one, anchor something to the transform
                // Step 1: Create a new node QuadTransformNode as a child of Root, and set the transform from quad[0].Transform
                // Step 2: Create your hologram and set it as a child of QuadTransformNode
                // Step 3: Set the QuadTransformNode tranform to a translation (location.x, location.y, 0)
            }
        }
    }
}
```

<span data-ttu-id="5a880-260">Шаги 1-3 сильно зависят от конкретной платформы или реализации, но темы должны быть похожи.</span><span class="sxs-lookup"><span data-stu-id="5a880-260">Steps 1-3 are highly dependent on your particular framework/implementation, but the themes should be similar.</span></span> <span data-ttu-id="5a880-261">Важно отметить, что четыре обычно не предназначены, просто представляет ограниченную двухмерную плоскость, локализованную в пространстве.</span><span class="sxs-lookup"><span data-stu-id="5a880-261">It is important to note that the Quad is not usually intended to be, is just represents a bounded 2D plane that is localized in space.</span></span> <span data-ttu-id="5a880-262">Так как ваш модуль или платформа знает, где четыре – и в корне объекты находятся по сравнению с четырьмя, самые голограммы будут размещены правильно.</span><span class="sxs-lookup"><span data-stu-id="5a880-262">By having your engine/framework know where the quad is and rooting your objects relative to the quad, your holograms will be located correctly.</span></span> <span data-ttu-id="5a880-263">Для получения более подробных сведений ознакомьтесь с нашими примерами на четырех, которые демонстрируют конкретные реализации.</span><span class="sxs-lookup"><span data-stu-id="5a880-263">For more detailed information please see our samples on quads which show specific implementations.</span></span>

### <a name="mesh"></a><span data-ttu-id="5a880-264">Сетчат</span><span class="sxs-lookup"><span data-stu-id="5a880-264">Mesh</span></span>

<span data-ttu-id="5a880-265">Сетки представляют геометрические представления объектов или сред.</span><span class="sxs-lookup"><span data-stu-id="5a880-265">Meshes represent geometric representations of objects or environments.</span></span> <span data-ttu-id="5a880-266">Подобно [пространственному](spatial-mapping.md)сопоставлению, индекс сетки и данные вершин, предоставляемые каждой сетке пространственных областей, используют тот же привычный макет, что и буферы вершин и индексов, которые используются для отрисовки сеток треугольников во всех современных API-интерфейсах отрисовки.</span><span class="sxs-lookup"><span data-stu-id="5a880-266">Much like [spatial mapping](spatial-mapping.md), mesh index and vertex data provided with each spatial surface mesh uses the same familiar layout as the vertex and index buffers that are used for rendering triangle meshes in all modern rendering APIs.</span></span> <span data-ttu-id="5a880-267">Ниже перечислены конкретные API-интерфейсы, используемые для ссылки на эти данные.</span><span class="sxs-lookup"><span data-stu-id="5a880-267">The specific APIs used to reference this data are as follows:</span></span>

```cs
void GetTriangleIndices(int[] indices);
void GetVertices(float[] vertices);
```

<span data-ttu-id="5a880-268">\* \* Примечание. Метод onвершины возвращает список вершин, каждый из трех кортежей значений с плавающей запятой которых представляет одну координату в координатах x, y и z.</span><span class="sxs-lookup"><span data-stu-id="5a880-268">\*\*Note: GetVertices returns a list of vertices where every 3-tuple of floating point values represents a single coordinate in cartesian x,y and z space.</span></span>

<span data-ttu-id="5a880-269">В следующем коде приведен пример создания списка треугольников из структуры сетки.</span><span class="sxs-lookup"><span data-stu-id="5a880-269">The following code provides an example of generating a triangle list from the mesh structure:</span></span>

```cs
uint[] indices = new uint[mesh.TriangleIndexCount];
float[] positions = new float[mesh.VertexCount * 3];

mesh.GetTriangleIndices(indices);
mesh.GetVertexPositions(positions);
```

<span data-ttu-id="5a880-270">Буферы индексов и вершин должны быть > = количество индексов или вершин, но в противном случае можно изменить размер произвольного размера, допуская эффективное использование памяти.</span><span class="sxs-lookup"><span data-stu-id="5a880-270">The index/vertex buffers must be >= the index/vertex counts, but otherwise can be arbitrarily sized allowing for efficient memory re-use.</span></span>

### <a name="developing-with-scene-understandings"></a><span data-ttu-id="5a880-271">Разработка с использованием сцен</span><span class="sxs-lookup"><span data-stu-id="5a880-271">Developing with Scene Understandings</span></span>

<span data-ttu-id="5a880-272">На этом этапе вы должны понимать основные строительные блоки сцены, посвященные среде выполнения и пакету SDK.</span><span class="sxs-lookup"><span data-stu-id="5a880-272">At this point you should understand the core building blocks of the Scene Understanding runtime and SDK.</span></span> <span data-ttu-id="5a880-273">Многие возможности и сложность основаны на шаблонах доступа, взаимодействии с трехмерными платформами и средствах, которые могут быть написаны поверх этих API для выполнения более сложных задач, таких как пространственное планирование, анализ комнаты, навигация, физика и т. д. Мы надеемся, что они записываются в примеры, которые будут надеяться вам в правильном направлении.</span><span class="sxs-lookup"><span data-stu-id="5a880-273">The bulk of the power and complexity lies in access patterns, interaction with 3d frameworks, and tools that can be written on top of these APIs to perform more advanced tasks like spatial planning, room analysis, navigation, physics etc... We hope to capture these in samples that should hopefully guide you in the proper direction to make your scenarios shine.</span></span> <span data-ttu-id="5a880-274">Если у вас есть образцы или сценарии, которые мы не используем, сообщите нам, и мы попытаемся попытаться документировать или обменять нужные объекты.</span><span class="sxs-lookup"><span data-stu-id="5a880-274">If there are samples/scenarios we are not addressing, please let us know and we will try to document/prototype what you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a880-275">См. также</span><span class="sxs-lookup"><span data-stu-id="5a880-275">See also</span></span>

* [<span data-ttu-id="5a880-276">пространственное сопоставление</span><span class="sxs-lookup"><span data-stu-id="5a880-276">spatial mapping</span></span>](spatial-mapping.md)