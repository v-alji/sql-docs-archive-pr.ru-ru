---
title: Добавление источника с помощью помощника по источнику | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b58b10508765580e0cffe9bd62099f3e2d69863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658975"
---
# <a name="add-a-source-using-source-assistant"></a><span data-ttu-id="a1897-102">Добавление источника с помощью помощника по источнику</span><span class="sxs-lookup"><span data-stu-id="a1897-102">Add a Source using Source Assistant</span></span>
  <span data-ttu-id="a1897-103">В этом разделе приведены шаги по добавлению нового источника с помощью помощника по источнику, а также список параметров, доступных в диалоговом окне **Добавление нового источника** , которое отображается при перетаскивании помощника по источнику в конструктор служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="a1897-103">This topic provides steps to add a new source using the Source Assistant and also lists the options that are available on the **Add New Source** dialog, which you will see when you drag-drop the Source Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-source-assistant-to-add-a-source"></a><span data-ttu-id="a1897-104">Добавление источника с помощью помощника по источнику</span><span class="sxs-lookup"><span data-stu-id="a1897-104">To use Source Assistant to add a source</span></span>  
  
1.  <span data-ttu-id="a1897-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , в который нужно добавить компонент источника.</span><span class="sxs-lookup"><span data-stu-id="a1897-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a source component to.</span></span>  
  
2.  <span data-ttu-id="a1897-106">Перетащите компонент **Помощник по источнику** из области элементов SSIS на вкладку **Поток данных** . Появится диалоговое окно **Добавление нового источника** .</span><span class="sxs-lookup"><span data-stu-id="a1897-106">Drag the **Source Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Source** dialog box.</span></span> <span data-ttu-id="a1897-107">В следующем разделе приведены подробные сведения о параметрах, доступных в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="a1897-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="a1897-108">Выберите тип назначения в списке **Типы** .</span><span class="sxs-lookup"><span data-stu-id="a1897-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="a1897-109">Выберите существующий диспетчер подключений в списке **Диспетчеры подключений** или создайте новый, выбрав пункт **\<New>** .</span><span class="sxs-lookup"><span data-stu-id="a1897-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="a1897-110">Если был выбран существующий диспетчер соединений, нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Добавление нового назначения** .</span><span class="sxs-lookup"><span data-stu-id="a1897-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="a1897-111">Должны быть показаны назначение и диспетчеры соединений, добавленные в поток данных.</span><span class="sxs-lookup"><span data-stu-id="a1897-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="a1897-112">Если для создания диспетчера подключений был выбран пункт **\<New>** , должно появиться диалоговое окно **Диспетчер подключений**, в котором можно указать параметры подключения.</span><span class="sxs-lookup"><span data-stu-id="a1897-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="a1897-113">После завершения создания нового диспетчера соединений в конструкторе служб SSIS будут показаны назначение и диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="a1897-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
