---
title: Диалоговое окно "Параметры построитель отчетов", "Параметры" (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10427"
ms.assetid: 423360de-9bed-462e-921f-60a5abab004f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 07bd4a7f9dfe1abd8ab76765cb1ac10ff5227066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657032"
---
# <a name="report-builder-options-dialog-box-settings-report-builder"></a><span data-ttu-id="98f00-102">Диалоговое окно «Параметры построителя отчетов» — «Настройки» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="98f00-102">Report Builder Options Dialog Box, Settings (Report Builder)</span></span>
  <span data-ttu-id="98f00-103">Нажмите кнопку **Построитель отчетов** и выберите **Параметры** , чтобы задать параметры для отображения последних файлов и подключений.</span><span class="sxs-lookup"><span data-stu-id="98f00-103">Click the **Report Builder** button and then click **Options** to set options for showing recent files and connections.</span></span> <span data-ttu-id="98f00-104">Можно также изменить сервер отчетов по умолчанию или добавить его, если сервер по умолчанию не задан.</span><span class="sxs-lookup"><span data-stu-id="98f00-104">You can also change the default report server, or add one if you don't have a default.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="98f00-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="98f00-105">UI element list</span></span>  
 <span data-ttu-id="98f00-106">**По умолчанию использовать этот сервер отчетов или сайт SharePoint**</span><span class="sxs-lookup"><span data-stu-id="98f00-106">**Use this report server or SharePoint site by default**</span></span>  
 <span data-ttu-id="98f00-107">Этот параметр может настроить администратор.</span><span class="sxs-lookup"><span data-stu-id="98f00-107">Your administrator may have configured this.</span></span> <span data-ttu-id="98f00-108">Значение может представлять собой URL-адрес правильного формата, начинающийся с http:// или https://.</span><span class="sxs-lookup"><span data-stu-id="98f00-108">The value can be a well-formed URL starting with http:// or https://.</span></span> <span data-ttu-id="98f00-109">Эта настройка определяет, какие соединения с источниками данных отображаются по умолчанию в мастере таблицы и матрицы и мастере диаграмм.</span><span class="sxs-lookup"><span data-stu-id="98f00-109">This setting determines which data source connections appear by default in the Table/Matrix and Chart wizards.</span></span> <span data-ttu-id="98f00-110">Кроме того, на этом сервере будут обрабатываться отчеты и можно указывать ссылки на ресурсы с этого сервера.</span><span class="sxs-lookup"><span data-stu-id="98f00-110">In addition, your reports will be processed on this server and you can reference resources from this server.</span></span>  
  
 <span data-ttu-id="98f00-111">Если выбрать другой сервер отчетов, может понадобиться перезапустить построитель отчетов, чтобы это изменение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="98f00-111">If you select a different report server, you may need to restart Report Builder in order for this change to take affect.</span></span>  
  
 <span data-ttu-id="98f00-112">**По умолчанию публиковать элементы отчета в эту папку**</span><span class="sxs-lookup"><span data-stu-id="98f00-112">**Publish report parts to this folder by default**</span></span>  
 <span data-ttu-id="98f00-113">Построитель отчетов сохранит публикуемые элементы отчета в эту папку.</span><span class="sxs-lookup"><span data-stu-id="98f00-113">Report Builder will save report parts that you publish to this folder.</span></span> <span data-ttu-id="98f00-114">Если папка еще не существует и имеются разрешения для создания папок на сервере отчетов, построитель отчетов создаст эту папку.</span><span class="sxs-lookup"><span data-stu-id="98f00-114">If the folder does not exist yet and you have permissions to create folders on the report server, Report Builder will create this folder.</span></span>  
  
 <span data-ttu-id="98f00-115">Чтобы этот параметр вступил в силу, не нужно перезапускать построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="98f00-115">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
 <span data-ttu-id="98f00-116">**Показывать следующее количество последних сайтов и серверов**</span><span class="sxs-lookup"><span data-stu-id="98f00-116">**Show this number of recent sites and servers**</span></span>  
 <span data-ttu-id="98f00-117">Укажите число последних сайтов и соединений, которое следует отображать в диалоговых окнах **Открытие отчета** и **Сохранение отчета** .</span><span class="sxs-lookup"><span data-stu-id="98f00-117">Specify the number of recent sites and connections to show in the **Open Report** and **Save As Report** dialog boxes.</span></span>  
  
 <span data-ttu-id="98f00-118">**Показывать следующее число последних соединений с общими наборами данных и источниками данных**</span><span class="sxs-lookup"><span data-stu-id="98f00-118">**Show this number of recent shared datasets and data source connections**</span></span>  
 <span data-ttu-id="98f00-119">Укажите число последних соединений с общими наборами данных и источниками данных, которое следует отображать в диалоговом окне **Свойства набора данных** и на странице **Выбор соединения с источником данных** мастера областей данных.</span><span class="sxs-lookup"><span data-stu-id="98f00-119">Specify the number of recent shared datasets and data source connections to show in the **Dataset Properties** dialog box and the **Choose a connection to a data source** page of the Data Regions Wizard.</span></span>  
  
 <span data-ttu-id="98f00-120">**Показывать следующее количество последних документов**</span><span class="sxs-lookup"><span data-stu-id="98f00-120">**Show this number of recent documents**</span></span>  
 <span data-ttu-id="98f00-121">Укажите число последних документов, которое следует отображать при нажатии кнопки «Построитель отчетов».</span><span class="sxs-lookup"><span data-stu-id="98f00-121">Specify the number of recent documents to show when you click the Report Builder button.</span></span>  
  
 <span data-ttu-id="98f00-122">**Очистить все списки последних элементов**</span><span class="sxs-lookup"><span data-stu-id="98f00-122">**Clear all recent item lists**</span></span>  
 <span data-ttu-id="98f00-123">Позволяет очистить текущие списки последних сайтов и серверов, общих наборов данных, соединений с общими источниками данных и документов.</span><span class="sxs-lookup"><span data-stu-id="98f00-123">Clear the current lists of recent sites and servers, shared datasets, shared data source connections, and documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f00-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="98f00-124">See Also</span></span>  
 [<span data-ttu-id="98f00-125">Справка построителя отчетов для диалоговых окон, панелей и мастеров</span><span class="sxs-lookup"><span data-stu-id="98f00-125">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
