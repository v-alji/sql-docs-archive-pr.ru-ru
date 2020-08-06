---
title: Редактор преобразования "Нечеткое группирование" (вкладка "Диспетчер соединений") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.connection.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 47b1446d-5331-473c-9cb5-a98b1f55bf5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2a8b0af9f36fdd386f7da375184fd4e4ec5c4be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667281"
---
# <a name="fuzzy-grouping-transformation-editor-connection-manager-tab"></a><span data-ttu-id="68788-102">Редактор преобразования «Нечеткое группирование» (вкладка «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="68788-102">Fuzzy Grouping Transformation Editor (Connection Manager Tab)</span></span>
  <span data-ttu-id="68788-103">Вкладка **Диспетчер соединений** в диалоговом окне **Редактор преобразования «Нечеткое группирование»** используется для выбора существующего соединения или для создания нового.</span><span class="sxs-lookup"><span data-stu-id="68788-103">Use the **Connection Manager** tab of the **Fuzzy Grouping Transformation Editor** dialog box to select an existing connection or create a new one.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68788-104">Сервер, указанный в соединении, должен работать под управлением [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68788-104">The server specified by the connection must be running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="68788-105">Преобразование "Нечеткое группирование" создает временные объекты в базе данных tempdb, размер которой может соответствовать полному вводу для преобразования.</span><span class="sxs-lookup"><span data-stu-id="68788-105">The Fuzzy Grouping transformation creates temporary data objects in tempdb that may be as large as the full input to the transformation.</span></span> <span data-ttu-id="68788-106">При выполнении преобразования запросы сервера выполняются в зависимости от этих временных объектов.</span><span class="sxs-lookup"><span data-stu-id="68788-106">While the transformation executes, it issues server queries against these temporary objects.</span></span> <span data-ttu-id="68788-107">Это может повлиять на общую производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="68788-107">This can affect overall server performance.</span></span>  
  
 <span data-ttu-id="68788-108">Дополнительные сведения о преобразовании «Нечеткое группирование» см. в разделе [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="68788-108">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="68788-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="68788-109">Options</span></span>  
 <span data-ttu-id="68788-110">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="68788-110">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="68788-111">Выберите в списке существующий диспетчер соединения OLE DB или создайте новое соединение с помощью кнопки **Создать** .</span><span class="sxs-lookup"><span data-stu-id="68788-111">Select an existing OLE DB connection manager by using the list box, or create a new connection by using the **New** button.</span></span>  
  
 <span data-ttu-id="68788-112">**Создать**</span><span class="sxs-lookup"><span data-stu-id="68788-112">**New**</span></span>  
 <span data-ttu-id="68788-113">Создайте новое соединение с помощью диалогового окна **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="68788-113">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68788-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="68788-114">See Also</span></span>  
 <span data-ttu-id="68788-115">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="68788-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="68788-116">Определение подобных строк данных с помощью преобразования «Нечеткое группирование»</span><span class="sxs-lookup"><span data-stu-id="68788-116">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
