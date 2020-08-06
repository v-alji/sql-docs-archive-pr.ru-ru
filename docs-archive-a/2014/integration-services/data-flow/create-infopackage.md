---
title: Создать InfoPackage | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9cd4a848-409f-4681-a390-1c49a2aadbd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95f6ddce4e97c0c21d9f77c432231d414770dbce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728569"
---
# <a name="create-infopackage"></a><span data-ttu-id="33d45-102">Создать InfoPackage</span><span class="sxs-lookup"><span data-stu-id="33d45-102">Create InfoPackage</span></span>
  <span data-ttu-id="33d45-103">Используйте диалоговое окно **Создать InfoPackage** для создания нового InfoPackage в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="33d45-103">Use the **Create InfoPackage** dialog box to create a new InfoPackage in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="33d45-104">Диалоговое окно **Создать InfoPackage** можно открыть на странице **Диспетчер соединений** **Редактора назначений SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="33d45-104">You can open the **Create InfoPackage** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="33d45-105">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="33d45-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="33d45-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="33d45-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="33d45-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="33d45-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="33d45-108">**Открытие диалогового окна «Создание InfoPackage»**</span><span class="sxs-lookup"><span data-stu-id="33d45-108">**To open the Create InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="33d45-109">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="33d45-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="33d45-110">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="33d45-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="33d45-111">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="33d45-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="33d45-112">На вкладке **Диспетчер соединений** в поле группы **Создание объектов SAP BW** выберите **InfoPackage**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="33d45-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoPackage**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="33d45-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="33d45-113">Options</span></span>  
 <span data-ttu-id="33d45-114">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="33d45-114">**InfoSource**</span></span>  
 <span data-ttu-id="33d45-115">Введите имя InfoSource, на основе которого должен быть создан новый InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="33d45-115">Enter the name of the InfoSource on which the new InfoPackage should be based.</span></span>  
  
 <span data-ttu-id="33d45-116">**Краткое описание**</span><span class="sxs-lookup"><span data-stu-id="33d45-116">**Short description**</span></span>  
 <span data-ttu-id="33d45-117">Введите описание нового InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="33d45-117">Enter a description for the new InfoPackage.</span></span>  
  
 <span data-ttu-id="33d45-118">**Исходная система**</span><span class="sxs-lookup"><span data-stu-id="33d45-118">**Source system**</span></span>  
 <span data-ttu-id="33d45-119">Выберите исходную систему, с которой должен быть связан новый InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="33d45-119">Select the source system with which the new InfoPackage should be associated.</span></span>  
  
 <span data-ttu-id="33d45-120">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="33d45-120">**Attributes**</span></span>  
 <span data-ttu-id="33d45-121">Указывает, что InfoPackage загрузит данные атрибутов.</span><span class="sxs-lookup"><span data-stu-id="33d45-121">Indicates that the InfoPackage will load attribute data.</span></span>  
  
 <span data-ttu-id="33d45-122">**Тексты**</span><span class="sxs-lookup"><span data-stu-id="33d45-122">**Texts**</span></span>  
 <span data-ttu-id="33d45-123">Указывает, что InfoPackage загрузит текстовые данные.</span><span class="sxs-lookup"><span data-stu-id="33d45-123">Indicates that the InfoPackage will load text data.</span></span>  
  
 <span data-ttu-id="33d45-124">**Транзакция**</span><span class="sxs-lookup"><span data-stu-id="33d45-124">**Transaction**</span></span>  
 <span data-ttu-id="33d45-125">Указывает, что InfoPackage загрузит данные транзакций.</span><span class="sxs-lookup"><span data-stu-id="33d45-125">Indicates that the InfoPackage will load transaction data.</span></span>  
  
 <span data-ttu-id="33d45-126">**Сохранить и активировать**</span><span class="sxs-lookup"><span data-stu-id="33d45-126">**Save & Activate**</span></span>  
 <span data-ttu-id="33d45-127">Сохраните и включите новый InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="33d45-127">Save and activate the new InfoPackage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d45-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="33d45-128">See Also</span></span>  
 [<span data-ttu-id="33d45-129">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="33d45-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
