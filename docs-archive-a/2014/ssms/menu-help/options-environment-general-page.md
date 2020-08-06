---
title: Параметры ("среда" — страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.SQLEnvironmentOptions
ms.assetid: c32ccdb8-2cf8-4c78-b474-a3abd3dbbd13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7712c568b478bd2ba958237ba3204246657b3a72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669229"
---
# <a name="options-environment-general-page"></a><span data-ttu-id="339f7-102">Параметры ("Среда" — "Общие")</span><span class="sxs-lookup"><span data-stu-id="339f7-102">Options (Environment-General Page)</span></span>
  <span data-ttu-id="339f7-103">Диалоговое окно **Параметры** используется для настройки действий среды [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] при запуске, общих параметров управления окнами и других общих настроек.</span><span class="sxs-lookup"><span data-stu-id="339f7-103">Use the **Options** dialog box to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] startup actions, general window management options, and other general settings.</span></span> <span data-ttu-id="339f7-104">В меню **Сервис** выберите пункт **Параметры**, откройте папку **Среда** и выберите пункт **Общие**.</span><span class="sxs-lookup"><span data-stu-id="339f7-104">On the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="339f7-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="339f7-105">UI element list</span></span>  
 <span data-ttu-id="339f7-106">**При запуске**</span><span class="sxs-lookup"><span data-stu-id="339f7-106">**At startup**</span></span>  
 <span data-ttu-id="339f7-107">Выберите действие, которое среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] будет выполнять при запуске.</span><span class="sxs-lookup"><span data-stu-id="339f7-107">Select the action for [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to perform when it is started.</span></span> <span data-ttu-id="339f7-108">Доступны следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="339f7-108">The options are:</span></span>  
  
-   <span data-ttu-id="339f7-109">**Открыть обозреватель объектов** — запрашивает об установке соединения, а затем открывает обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="339f7-109">**Open Object Explorer** prompts for a connection and then opens Object Explorer.</span></span>  
  
-   <span data-ttu-id="339f7-110">**Открыть новое окно запроса** — запрашивает об установке соединения, а затем открывает редактор SQL-запросов.</span><span class="sxs-lookup"><span data-stu-id="339f7-110">**Open new query window** prompts for a connection and then opens SQL Query Editor.</span></span>  
  
-   <span data-ttu-id="339f7-111">**Открыть обозреватель объектов и новый запрос** — запрашивает об установке соединения, а затем открывает обозреватель объектов и редактор SQL-запросов с помощью этого соединения.</span><span class="sxs-lookup"><span data-stu-id="339f7-111">**Open Object Explorer and new query** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.</span></span>  
  
-   <span data-ttu-id="339f7-112">**Открыть пустую среду** — открывает среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] без окна редактора SQL-запросов и без соединения обозревателя объектов с сервером.</span><span class="sxs-lookup"><span data-stu-id="339f7-112">**Open empty environment** opens [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] without a SQL Query editor window and without connecting Object Explorer to a server.</span></span>  
  
 <span data-ttu-id="339f7-113">**Скрыть системные объекты в обозревателе объектов**</span><span class="sxs-lookup"><span data-stu-id="339f7-113">**Hide system objects in Object Explorer**</span></span>  
 <span data-ttu-id="339f7-114">Установите этот флажок для удаления системных баз данных, системных таблиц, системных представлений и системных хранимых процедур из представления в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="339f7-114">Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer.</span></span> <span data-ttu-id="339f7-115">Системные функции и системные типы данных не скрываются.</span><span class="sxs-lookup"><span data-stu-id="339f7-115">System functions and system data types are not hidden.</span></span> <span data-ttu-id="339f7-116">Этот параметр применяется только к экземплярам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и не оказывает влияния на серверы, уже подключенные к обозревателю объектов.</span><span class="sxs-lookup"><span data-stu-id="339f7-116">This option only applies to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and does not affect servers already connected in Object Explorer.</span></span>  
  
## <a name="environment-layout"></a><span data-ttu-id="339f7-117">Макет среды</span><span class="sxs-lookup"><span data-stu-id="339f7-117">Environment Layout</span></span>  
 <span data-ttu-id="339f7-118">Для переключения среды из режима «документы с вкладками» в режим многодокументного интерфейса (MDI) необходимо закрыть и вновь открыть среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="339f7-118">You must close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change between tabbed document and multiple-document interface (MDI) environment mode.</span></span>  
  
 <span data-ttu-id="339f7-119">**Документы с вкладками**</span><span class="sxs-lookup"><span data-stu-id="339f7-119">**Tabbed documents**</span></span>  
 <span data-ttu-id="339f7-120">Выберите этот параметр для отображения внутри редакторов окон с документами, которые связаны между собой вкладками.</span><span class="sxs-lookup"><span data-stu-id="339f7-120">Select this option to display document windows that are tabbed together within editors.</span></span> <span data-ttu-id="339f7-121">Окна документов с вкладками полезно применять для организации нескольких открытых документов и для переключения от одного такого документа к другому.</span><span class="sxs-lookup"><span data-stu-id="339f7-121">Tabbed document windows are useful for organizing and switching between multiple open documents.</span></span>  
  
 <span data-ttu-id="339f7-122">**Среда MDI**</span><span class="sxs-lookup"><span data-stu-id="339f7-122">**MDI environment**</span></span>  
 <span data-ttu-id="339f7-123">Выберите этот параметр для открытия документов в среде MDI.</span><span class="sxs-lookup"><span data-stu-id="339f7-123">Select this option to open documents in a MDI environment.</span></span> <span data-ttu-id="339f7-124">Использовать окна с документами в режиме MDI полезно в тех случаях, когда необходимо высвободить пространство на экране, которое в ином случае (в режиме документов с вкладками) было бы занято вкладками.</span><span class="sxs-lookup"><span data-stu-id="339f7-124">MDI document windows are useful for gaining the screen space that is otherwise taken up by the tabs in the tabbed documents environment.</span></span> <span data-ttu-id="339f7-125">При работе в режиме MDI можно переходить от одного документа к другому, используя сочетание клавиш CTRL+TAB или выбирая в меню **Окно** команды расположения сверху вниз или слева направо.</span><span class="sxs-lookup"><span data-stu-id="339f7-125">When working in MDI mode, you can switch between documents by pressing CTRL+TAB, or you can use the tile options located on the **Window** menu.</span></span>  
  
## <a name="docked-tool-window-behavior"></a><span data-ttu-id="339f7-126">Поведение закрепленного окна инструментов</span><span class="sxs-lookup"><span data-stu-id="339f7-126">Docked Tool Window Behavior</span></span>  
 <span data-ttu-id="339f7-127">**Кнопка «Закрыть» действует только на активной вкладке**</span><span class="sxs-lookup"><span data-stu-id="339f7-127">**Close button affects active tab only**</span></span>  
 <span data-ttu-id="339f7-128">Указывает, что когда этот флажок установлен, закрываются не все закрепленные окна инструментов, а только то окно инструментов, которое в данный момент имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="339f7-128">Specifies that when this check box is selected, only the tool window that has focus currently is closed and not all of the tool windows in the docked set.</span></span> <span data-ttu-id="339f7-129">По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="339f7-129">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="339f7-130">**Кнопка «Автоматически скрыть» действует только на активной вкладке**</span><span class="sxs-lookup"><span data-stu-id="339f7-130">**Auto Hide button affects active tab only**</span></span>  
 <span data-ttu-id="339f7-131">Указывает, что когда этот флажок установлен, автоматически скрываются не все закрепленные окна инструментов, а только то окно инструментов, которое в данный момент имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="339f7-131">Specifies that when this check box is selected, only the tool window that has focus currently is hidden automatically, not all of the tool windows in the docked set.</span></span> <span data-ttu-id="339f7-132">По умолчанию этот флажок снят.</span><span class="sxs-lookup"><span data-stu-id="339f7-132">By default, this check box is cleared.</span></span>  
  
## <a name="display"></a><span data-ttu-id="339f7-133">Отображение</span><span class="sxs-lookup"><span data-stu-id="339f7-133">Display</span></span>  
 <span data-ttu-id="339f7-134">**Включать в список недавно использованных файлов n элементов**</span><span class="sxs-lookup"><span data-stu-id="339f7-134">**Display n files in recently used list**</span></span>  
 <span data-ttu-id="339f7-135">Задает число недавно открывавшихся проектов и недавно использованных файлов, которые отображаются в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="339f7-135">Customizes the number of recent projects and recent files that appear on the **File** menu.</span></span> <span data-ttu-id="339f7-136">Введите число от 1 до 24.</span><span class="sxs-lookup"><span data-stu-id="339f7-136">Type a number between 1 and 24.</span></span> <span data-ttu-id="339f7-137">Значение по умолчанию — 4.</span><span class="sxs-lookup"><span data-stu-id="339f7-137">The default is 4.</span></span> <span data-ttu-id="339f7-138">Это удобный способ получения недавно использованных проектов скриптов и проектов файлов и скриптов.</span><span class="sxs-lookup"><span data-stu-id="339f7-138">This is an easy way to retrieve recently used script projects and files and script projects.</span></span>  
  
  
