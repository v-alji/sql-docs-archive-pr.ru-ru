---
title: Настройка свойств сборщика данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollectionprop.advanced.f1
- sql12.swb.dc.datacollectionprop.general.f1
ms.assetid: cf98f57d-5a6d-4bc3-bf10-783e460fc63d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05172c2c831ec649269512a625be069cdc67047a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734142"
---
# <a name="configure-properties-of-a-data-collector"></a><span data-ttu-id="6559a-102">Настройка свойств сборщика данных</span><span class="sxs-lookup"><span data-stu-id="6559a-102">Configure Properties of a Data Collector</span></span>
  <span data-ttu-id="6559a-103">В этом разделе рассматривается настройка свойств сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="6559a-103">This topic discusses how you can configure the properties of a data collector.</span></span>  
  
## <a name="data-collection-properties-general-tab"></a><span data-ttu-id="6559a-104">Свойства сбора данных (вкладка «Общие»)</span><span class="sxs-lookup"><span data-stu-id="6559a-104">Data Collection Properties (General Tab)</span></span>  
 <span data-ttu-id="6559a-105">Эта страница используется для настройки параметров хранилища данных управления и указания места хранения собранных данных перед передачей в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="6559a-105">Use this page to configure settings for the management data warehouse and specify where collected data should be stored before it is uploaded to the data warehouse.</span></span>  
  
 <span data-ttu-id="6559a-106">**Включить сбор данных**</span><span class="sxs-lookup"><span data-stu-id="6559a-106">**Enable Data Collection**</span></span>  
 <span data-ttu-id="6559a-107">Выберите, чтобы включить сбор данных.</span><span class="sxs-lookup"><span data-stu-id="6559a-107">Select to enable data collection.</span></span> <span data-ttu-id="6559a-108">Результат этого действия такой же, как при запуске хранимой процедуры sp_syscollector_enable_collector.</span><span class="sxs-lookup"><span data-stu-id="6559a-108">This has the same effect as running the sp_syscollector_enable_collector stored procedure.</span></span> <span data-ttu-id="6559a-109">При снятии флажка сбор данных отключается, результат такой же, как при запуске хранимой процедуры sp_syscollector_disable_collector.</span><span class="sxs-lookup"><span data-stu-id="6559a-109">Clearing this check box disables data collection and has the same effect as running the sp_syscollector_disable_collector stored procedure.</span></span>  
  
 <span data-ttu-id="6559a-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="6559a-110">**Server**</span></span>  
 <span data-ttu-id="6559a-111">Отображает имя сервера, на котором будет размещено хранилище данных управления.</span><span class="sxs-lookup"><span data-stu-id="6559a-111">Displays the name of the server that will host the management data warehouse</span></span>  
  
 <span data-ttu-id="6559a-112">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="6559a-112">**Database name**</span></span>  
 <span data-ttu-id="6559a-113">Отображает имя реляционной базы данных, которая используется для хранилища управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="6559a-113">Displays the name of the relational database that is used for the management data warehouse.</span></span>  
  
 <span data-ttu-id="6559a-114">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="6559a-114">**Test Connection**</span></span>  
 <span data-ttu-id="6559a-115">Проверяет соединение с указанным **Сервером** с использованием данных, предоставленных при настройке сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="6559a-115">Test the connection to the specified **Server** using information provided when data collection is configured.</span></span>  
  
 <span data-ttu-id="6559a-116">**Каталог кэша**</span><span class="sxs-lookup"><span data-stu-id="6559a-116">**Cache directory**</span></span>  
 <span data-ttu-id="6559a-117">Указывает каталог, в котором хранятся собранные данные на локальном компьютере до их передачи в хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="6559a-117">Specifies the directory where collected data is stored on the system collecting the data before it is uploaded to the management data warehouse.</span></span> <span data-ttu-id="6559a-118">Если **Каталог кэша** не указан, сборщик данных предпринимает попытку обнаружить переменные среды %TEMP% и %TMP% и использует одно из этих мест в качестве временного хранилища по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6559a-118">If **Cache directory** is not specified, the data collector attempts to locate the %TEMP% and %TMP% environment variables and use one these locations as the default location for temporary storage.</span></span> <span data-ttu-id="6559a-119">Если эти переменные среды не заданы, выдается ошибка и запрос для создания каталога кэша.</span><span class="sxs-lookup"><span data-stu-id="6559a-119">If these environment variables are not configured, an error occurs and you are prompted to create a cache directory.</span></span>  
  
## <a name="data-collection-properties-advanced-tab"></a><span data-ttu-id="6559a-120">Свойства сбора данных (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="6559a-120">Data Collection Properties (Advanced Tab)</span></span>  
 <span data-ttu-id="6559a-121">Эта страница используется для настройки параметров повторных попыток соединения с хранилищем данных управления.</span><span class="sxs-lookup"><span data-stu-id="6559a-121">Use this page to configure the retry settings for the connection to the management data warehouse.</span></span>  
  
 <span data-ttu-id="6559a-122">**Количество повторных попыток в случае ошибки передачи**</span><span class="sxs-lookup"><span data-stu-id="6559a-122">**Number of times to retry if upload fails**</span></span>  
 <span data-ttu-id="6559a-123">Указывает число повторных попыток передачи в хранилище управляющих данных, если передача завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6559a-123">Specifies the number of times to retry an upload to the management data warehouse if an upload fails.</span></span> <span data-ttu-id="6559a-124">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="6559a-124">The default is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6559a-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="6559a-125">See Also</span></span>  
 <span data-ttu-id="6559a-126">[Управление сбором данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="6559a-126">[Manage Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="6559a-127">Настройка хранилища данных управления (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6559a-127">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
