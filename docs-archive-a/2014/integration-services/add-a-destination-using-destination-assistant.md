---
title: Добавление назначения с помощью помощника по назначениям | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 747a0de0-3c2f-4d31-a692-7111fc0911d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd36828a7bab7fb33b86765f9f064b6406a17a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656533"
---
# <a name="add-a-destination-using-destination-assistant"></a><span data-ttu-id="e97d4-102">Добавление назначения с помощью помощника по назначениям</span><span class="sxs-lookup"><span data-stu-id="e97d4-102">Add a Destination using Destination Assistant</span></span>
  <span data-ttu-id="e97d4-103">В этом разделе приведены шаги по добавлению нового назначения с помощью помощника по назначениям, а также приведен список параметров, доступных в диалоговом окне **Добавление нового назначения** , которое отображается при перетаскивании помощника по назначениям в конструктор служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="e97d4-103">This topic provides steps to add a new destination using the Destination Assistant and also lists the options that are available on the **Add New Destination** dialog, which you will see when you drag-drop the Destination Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-destination-assistant-to-add-a-destination"></a><span data-ttu-id="e97d4-104">Добавление назначения с помощью помощника по назначениям</span><span class="sxs-lookup"><span data-stu-id="e97d4-104">To use Destination Assistant to add a destination</span></span>  
  
1.  <span data-ttu-id="e97d4-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , в который нужно добавить компонент назначения.</span><span class="sxs-lookup"><span data-stu-id="e97d4-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a destination component to.</span></span>  
  
2.  <span data-ttu-id="e97d4-106">Перетащите компонент **Помощник по назначениям** из области элементов SSIS на вкладку **Поток данных** . Появится диалоговое окно **Добавление нового назначения** .</span><span class="sxs-lookup"><span data-stu-id="e97d4-106">Drag the **Destination Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Destination** dialog box.</span></span> <span data-ttu-id="e97d4-107">В следующем разделе приведены подробные сведения о параметрах, доступных в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="e97d4-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="e97d4-108">Выберите тип назначения в списке **Типы** .</span><span class="sxs-lookup"><span data-stu-id="e97d4-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="e97d4-109">Выберите существующий диспетчер подключений в списке **Диспетчеры подключений** или создайте новый, выбрав пункт **\<New>** .</span><span class="sxs-lookup"><span data-stu-id="e97d4-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="e97d4-110">Если был выбран существующий диспетчер соединений, нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Добавление нового назначения** .</span><span class="sxs-lookup"><span data-stu-id="e97d4-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="e97d4-111">Должны быть показаны назначение и диспетчеры соединений, добавленные в поток данных.</span><span class="sxs-lookup"><span data-stu-id="e97d4-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="e97d4-112">Если для создания диспетчера подключений был выбран пункт **\<New>** , должно появиться диалоговое окно **Диспетчер подключений**, в котором можно указать параметры подключения.</span><span class="sxs-lookup"><span data-stu-id="e97d4-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="e97d4-113">После завершения создания нового диспетчера соединений в конструкторе служб SSIS будут показаны назначение и диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="e97d4-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
