---
title: Выбор таблицы измерения и ключей (мастер медленно изменяющихся измерений) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.selecttableandkeys.f1
ms.assetid: 01e0495f-de35-4607-ba19-0539e801e8fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 671c66a8a5d5f1f4f5201fd8c9ecc144540d8b68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752299"
---
# <a name="select-a-dimension-table-and-keys-slowly-changing-dimension-wizard"></a><span data-ttu-id="088b9-102">Выбрать таблицу измерения и ключи (мастер медленно изменяющихся измерений)</span><span class="sxs-lookup"><span data-stu-id="088b9-102">Select a Dimension Table and Keys (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="088b9-103">Страница **Выбор таблицы измерения и ключей** позволяет выбрать для загрузки таблицу измерения.</span><span class="sxs-lookup"><span data-stu-id="088b9-103">Use the **Select a Dimension Table and Keys** page to select a dimension table to load.</span></span> <span data-ttu-id="088b9-104">Сопоставьте столбцы из потока с данными столбцов, которые нужно загрузить.</span><span class="sxs-lookup"><span data-stu-id="088b9-104">Map columns from the data flow to the columns that will be loaded.</span></span>  
  
 <span data-ttu-id="088b9-105">Дополнительные сведения о работе этого мастера см. в разделе [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="088b9-105">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="088b9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="088b9-106">Options</span></span>  
 <span data-ttu-id="088b9-107">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="088b9-107">**Connection manager**</span></span>  
 <span data-ttu-id="088b9-108">Выберите из списка существующий диспетчер соединений OLE DB или нажмите кнопку **Создать** , чтобы создать диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="088b9-108">Select an existing OLE DB connection manager from the list, or click **New** to create an OLE DB connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="088b9-109">Мастер медленно изменяющихся измерений поддерживает только диспетчеры соединений OLE DB и подключения к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="088b9-109">The Slowly Changing Dimension Wizard only supports OLE DB connection managers, and only supports connections to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="088b9-110">**Создать**</span><span class="sxs-lookup"><span data-stu-id="088b9-110">**New**</span></span>  
 <span data-ttu-id="088b9-111">В диалоговом окне **Настройка диспетчера соединений OLE DB** выберите существующий диспетчер соединений или щелкните **Создать** для создания нового соединения OLE DB.</span><span class="sxs-lookup"><span data-stu-id="088b9-111">Use the **Configure OLE DB Connection Manager** dialog box to select an existing connection manager, or click **New** to create a new OLE DB connection.</span></span>  
  
 <span data-ttu-id="088b9-112">**Таблица или представление**</span><span class="sxs-lookup"><span data-stu-id="088b9-112">**Table or View**</span></span>  
 <span data-ttu-id="088b9-113">Выберите таблицу или представление из списка.</span><span class="sxs-lookup"><span data-stu-id="088b9-113">Select a table or view from the list.</span></span>  
  
 <span data-ttu-id="088b9-114">**Входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="088b9-114">**Input Columns**</span></span>  
 <span data-ttu-id="088b9-115">Выберите из списка входные столбцы, для которых можно указать сопоставление.</span><span class="sxs-lookup"><span data-stu-id="088b9-115">Select from the list of input columns for which you may specify mapping.</span></span>  
  
 <span data-ttu-id="088b9-116">**Столбцы измерений**</span><span class="sxs-lookup"><span data-stu-id="088b9-116">**Dimension Columns**</span></span>  
 <span data-ttu-id="088b9-117">Просмотр всех доступных столбцов измерений.</span><span class="sxs-lookup"><span data-stu-id="088b9-117">View all available dimension columns.</span></span>  
  
 <span data-ttu-id="088b9-118">**Тип ключа**</span><span class="sxs-lookup"><span data-stu-id="088b9-118">**Key Type**</span></span>  
 <span data-ttu-id="088b9-119">Выберите один из столбцов измерений в качестве бизнес-ключа.</span><span class="sxs-lookup"><span data-stu-id="088b9-119">Select one of the dimension columns to be the business key.</span></span> <span data-ttu-id="088b9-120">Необходимо иметь один бизнес-ключ.</span><span class="sxs-lookup"><span data-stu-id="088b9-120">You must have one business key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088b9-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="088b9-121">See Also</span></span>  
 [<span data-ttu-id="088b9-122">Настройка выходов с помощью мастера медленно изменяющихся измерений</span><span class="sxs-lookup"><span data-stu-id="088b9-122">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
