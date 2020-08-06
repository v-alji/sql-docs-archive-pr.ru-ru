---
title: Соединение с отчетом или веб-каналом данных (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76dd51c32d13e64b0368267ba7ac66aa6d76a784
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656726"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a><span data-ttu-id="1276c-102">Соединение с отчетом или веб-каналом данных (SSAS)</span><span class="sxs-lookup"><span data-stu-id="1276c-102">Connect to a Report or Data Feed (SSAS)</span></span>
  <span data-ttu-id="1276c-103">Эта страница **мастера импорта таблиц** позволяет подключиться к потоку данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-103">This page of the **Table Import Wizard** enables you to connect to a data feed.</span></span> <span data-ttu-id="1276c-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="1276c-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="from-a-report"></a><span data-ttu-id="1276c-105">Из отчета</span><span class="sxs-lookup"><span data-stu-id="1276c-105">From a Report</span></span>  
 <span data-ttu-id="1276c-106">**Понятное имя подключения**</span><span class="sxs-lookup"><span data-stu-id="1276c-106">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="1276c-107">Введите понятное имя для соединения с потоком данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-107">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="1276c-108">**Путь отчета**</span><span class="sxs-lookup"><span data-stu-id="1276c-108">**Report Path**</span></span>  
 <span data-ttu-id="1276c-109">Перечисляет URL-адреса для отчета служб SQL Server Reporting Services, который формирует каналы данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-109">Lists the URL for a SQL Server Reporting Services report that generates data feeds.</span></span> <span data-ttu-id="1276c-110">Нажмите кнопку **Обзор** , чтобы указать URL-адрес для отчета.</span><span class="sxs-lookup"><span data-stu-id="1276c-110">Click **Browse** to specify the URL for the report.</span></span>  
  
 <span data-ttu-id="1276c-111">Щелкните **Просмотр отчета**, чтобы просмотреть отчет.</span><span class="sxs-lookup"><span data-stu-id="1276c-111">Click **View Report** to display the report.</span></span>  
  
 <span data-ttu-id="1276c-112">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="1276c-112">**Browse**</span></span>  
 <span data-ttu-id="1276c-113">Перейдите в расположение, где находится отчет.</span><span class="sxs-lookup"><span data-stu-id="1276c-113">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="1276c-114">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="1276c-114">**Advanced**</span></span>  
 <span data-ttu-id="1276c-115">Задание дополнительных свойств соединения с помощью диалогового окна « **Задание дополнительных свойств** ».</span><span class="sxs-lookup"><span data-stu-id="1276c-115">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="1276c-116">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="1276c-116">**Test Connection**</span></span>  
 <span data-ttu-id="1276c-117">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="1276c-117">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="1276c-118">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="1276c-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-an-azure-datamarket-dataset"></a><span data-ttu-id="1276c-119">Из набора данных Azure DataMarket</span><span class="sxs-lookup"><span data-stu-id="1276c-119">From an Azure DataMarket Dataset</span></span>  
 <span data-ttu-id="1276c-120">**Понятное имя подключения**</span><span class="sxs-lookup"><span data-stu-id="1276c-120">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="1276c-121">Введите понятное имя для соединения с потоком данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-121">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="1276c-122">**URL-адрес потока данных**</span><span class="sxs-lookup"><span data-stu-id="1276c-122">**Data Feed URL**</span></span>  
 <span data-ttu-id="1276c-123">Укажите полный путь к сервисному документу Atom (ATOMSVC, ATOM), URL-адрес для единичного потока данных или нажмите кнопку **Обзор** , чтобы выбрать сервисный документ Atom.</span><span class="sxs-lookup"><span data-stu-id="1276c-123">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="1276c-124">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="1276c-124">**Browse**</span></span>  
 <span data-ttu-id="1276c-125">Перейдите в расположение, где находится отчет.</span><span class="sxs-lookup"><span data-stu-id="1276c-125">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="1276c-126">Нажмите кнопку **Просмотр доступных наборов Azure DataMarket** для отображения доступных наборов.</span><span class="sxs-lookup"><span data-stu-id="1276c-126">Click **View available Azure DataMarket datasets** to display available datasets.</span></span>  
  
 <span data-ttu-id="1276c-127">**Ключ учетной записи**</span><span class="sxs-lookup"><span data-stu-id="1276c-127">**Account key**</span></span>  
 <span data-ttu-id="1276c-128">Укажите ключ учетной записи, используемый для доступа к подпискам набора данных Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="1276c-128">Specify the account key used to access your Azure Marketplace dataset subscriptions.</span></span>  
  
 <span data-ttu-id="1276c-129">**Найдено**</span><span class="sxs-lookup"><span data-stu-id="1276c-129">**Find**</span></span>  
 <span data-ttu-id="1276c-130">Найдите ключ учетной записи, связанный с учетной записью Windows Live.</span><span class="sxs-lookup"><span data-stu-id="1276c-130">Locate an account key associated with a Windows Live account.</span></span>  
  
 <span data-ttu-id="1276c-131">**Сохранить мой ключ учетной записи**</span><span class="sxs-lookup"><span data-stu-id="1276c-131">**Save my account key**</span></span>  
 <span data-ttu-id="1276c-132">Сохраняет ключ учетной записи (зашифрованный) с подключением к данным.</span><span class="sxs-lookup"><span data-stu-id="1276c-132">Saves the account key (encrypted) with the data connection.</span></span>  
  
 <span data-ttu-id="1276c-133">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="1276c-133">**Advanced**</span></span>  
 <span data-ttu-id="1276c-134">Задание дополнительных свойств соединения с помощью диалогового окна « **Задание дополнительных свойств** ».</span><span class="sxs-lookup"><span data-stu-id="1276c-134">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="1276c-135">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="1276c-135">**Test Connection**</span></span>  
 <span data-ttu-id="1276c-136">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="1276c-136">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="1276c-137">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="1276c-137">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-other-feeds"></a><span data-ttu-id="1276c-138">Из других потоков</span><span class="sxs-lookup"><span data-stu-id="1276c-138">From Other Feeds</span></span>  
 <span data-ttu-id="1276c-139">**Понятное имя подключения**</span><span class="sxs-lookup"><span data-stu-id="1276c-139">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="1276c-140">Введите понятное имя для соединения с потоком данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-140">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="1276c-141">**URL-адрес потока данных**</span><span class="sxs-lookup"><span data-stu-id="1276c-141">**Data Feed URL**</span></span>  
 <span data-ttu-id="1276c-142">Укажите полный путь к сервисному документу Atom (ATOMSVC, ATOM), URL-адрес для единичного потока данных или нажмите кнопку **Обзор** , чтобы выбрать сервисный документ Atom.</span><span class="sxs-lookup"><span data-stu-id="1276c-142">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="1276c-143">Нажмите **Включить все столбцы потока** , чтобы указать, следует ли импортировать все столбцы потока данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-143">Click **Include all feed columns** to specify whether all the data feed columns are imported.</span></span>  
  
 <span data-ttu-id="1276c-144">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="1276c-144">**Browse**</span></span>  
 <span data-ttu-id="1276c-145">Перейдите в расположение, в котором доступен поток данных.</span><span class="sxs-lookup"><span data-stu-id="1276c-145">Navigate to a location where a data feed is available.</span></span>  
  
 <span data-ttu-id="1276c-146">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="1276c-146">**Advanced**</span></span>  
 <span data-ttu-id="1276c-147">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="1276c-147">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="1276c-148">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="1276c-148">**Test Connection**</span></span>  
 <span data-ttu-id="1276c-149">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="1276c-149">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="1276c-150">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="1276c-150">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
