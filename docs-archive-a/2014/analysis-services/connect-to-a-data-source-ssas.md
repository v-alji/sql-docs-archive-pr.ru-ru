---
title: Подключение к источнику данных (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndatasource.f1
ms.assetid: 1e2b17e9-092b-4af1-8a58-c52b8fe10ff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4fe7f7d5b31118369b8ce2a855b955e44f661dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656742"
---
# <a name="connect-to-a-data-source-ssas"></a><span data-ttu-id="4f390-102">Подключение к источнику данных (SSAS)</span><span class="sxs-lookup"><span data-stu-id="4f390-102">Connect to a Data Source (SSAS)</span></span>
  <span data-ttu-id="4f390-103">На этой странице **мастера импорта таблиц** создается новое соединение с источником данных. Поддерживаются разнообразные источники данных, в том числе реляционные базы данных, каналы данных и файлы.</span><span class="sxs-lookup"><span data-stu-id="4f390-103">This page of the **Table Import Wizard** enables you to create a new data source connection to a variety of data sources, such as relational databases, data feeds, and files.</span></span> <span data-ttu-id="4f390-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="4f390-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="4f390-105">Для соединения с источником данных необходимо, чтобы на компьютере был установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="4f390-105">To connect to a data source, you must have the appropriate provider installed on your machine.</span></span> <span data-ttu-id="4f390-106">На сервере базы данных рабочей области должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="4f390-106">You must also have the appropriate provider installed on the workspace database server.</span></span> <span data-ttu-id="4f390-107">Для 32-разрядных (x86) серверов должны быть установлены 32-разрядные поставщики.</span><span class="sxs-lookup"><span data-stu-id="4f390-107">For 32-bit (x86) servers, 32-bit providers must be installed.</span></span> <span data-ttu-id="4f390-108">Для 64-разрядных (x64) серверов должны быть установлены 64-разрядные поставщики.</span><span class="sxs-lookup"><span data-stu-id="4f390-108">For 64-bit (x64) servers, 64-bit providers must be installed.</span></span>  
  
 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] <span data-ttu-id="4f390-109">всегда выполняется в 32-разрядном процессе, независимо от архитектуры.</span><span class="sxs-lookup"><span data-stu-id="4f390-109">always runs in a 32-bit process, regardless of architecture.</span></span> <span data-ttu-id="4f390-110">Запуская [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] на 64-разрядном компьютере, следует учитывать следующие факторы при установке поставщиков данных.</span><span class="sxs-lookup"><span data-stu-id="4f390-110">When running [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] on a 64-bit machine, you should be aware of the following when installing data providers:</span></span>  
  
-   <span data-ttu-id="4f390-111">Для поставщиков, поддерживающих параллельную установку 32-разрядных и 64-разрядных поставщиков, необходимо установить оба поставщика.</span><span class="sxs-lookup"><span data-stu-id="4f390-111">For providers that support side-by-side installation of 32-bit and 64-bit providers, you should install both providers.</span></span>  
  
-   <span data-ttu-id="4f390-112">При установке поставщика ACE следует установить 64-разрядную версию поставщика.</span><span class="sxs-lookup"><span data-stu-id="4f390-112">For the ACE provider, you must install the 64-bit version of the provider.</span></span> <span data-ttu-id="4f390-113">Microsoft Office автоматически устанавливает поставщика ACE, поэтому не следует запускать 32-разрядную версию Microsoft Office на 64-разрядном компьютере с сервером базы данных рабочей области.</span><span class="sxs-lookup"><span data-stu-id="4f390-113">Because Office automatically installs the ACE provider, you should not run a 32-bit version of Microsoft Office on a 64-bit machine hosting the workspace database server.</span></span>  
  
     <span data-ttu-id="4f390-114">Поставщик ACE используется для импорта текстовых файлов, а также файлов Excel и Access.</span><span class="sxs-lookup"><span data-stu-id="4f390-114">The ACE provider is used to import from Text, Excel, and Access files.</span></span> <span data-ttu-id="4f390-115">Если поддержка этих данных источников не требуется, можно запустить 32-разрядную версию Microsoft Office на компьютере, на котором выполняется 64-разрядный сервер базы данных рабочей области.</span><span class="sxs-lookup"><span data-stu-id="4f390-115">If support for these data sources is not needed, you can then run a 32-bit version of Microsoft Office on a machine running a 64-bit workspace database server.</span></span>  
  
-   <span data-ttu-id="4f390-116">Для других поставщиков, не поддерживающих параллельную установку 32-разрядных и 64-разрядных поставщиков, требуется установка 32-разрядного поставщика.</span><span class="sxs-lookup"><span data-stu-id="4f390-116">For other providers that do not support side-by-side installation of 32-bit and 64-bit providers, you must install the 32-bit provider.</span></span> <span data-ttu-id="4f390-117">Если доступны только 64-разрядные компьютеры, необходимо использовать удаленный компьютер с 64-разрядным поставщиком, установленным как сервер базы данных рабочей области.</span><span class="sxs-lookup"><span data-stu-id="4f390-117">If only 64-bit machines are available, you must use a remote machine with a 64-bit provider installed as the workspace database server.</span></span>  
  
  
