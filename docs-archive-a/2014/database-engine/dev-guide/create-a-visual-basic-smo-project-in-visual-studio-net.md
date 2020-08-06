---
title: Создание Visual Basic проекта SMO в Visual Studio .NET | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic [SMO]
ms.assetid: d7a3892c-0f1c-4c4d-8480-b58dce3720bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 844d27ab6aadbc972c6282c79adb13e15d55c322
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751444"
---
# <a name="create-a-visual-basic-smo-project-in-visual-studio-net"></a><span data-ttu-id="99147-102">Создание проекта SMO на языке Visual Basic в среде Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="99147-102">Create a Visual Basic SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="99147-103">В данном разделе описывается, как построить простое консольное приложение командной строки SMO.</span><span class="sxs-lookup"><span data-stu-id="99147-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="99147-104">В этом примере импортируются пространства имен, что позволяет программе ссылаться на типы объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="99147-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="99147-105">Импорт пространства имен `Agent` необязателен.</span><span class="sxs-lookup"><span data-stu-id="99147-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="99147-106">Его следует выполнить при написании программы, в которой используется агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99147-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="99147-107">Пространство имен `Common` требуется для установления безопасного соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99147-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="99147-108">Пространство имен `SqlClient` используется для обработки ошибок, связанных с исключениями SQL.</span><span class="sxs-lookup"><span data-stu-id="99147-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-basic-smo-project-in-visual-studionet"></a><span data-ttu-id="99147-109">Создание проекта SMO на языке Visual Basic в среде Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="99147-109">Creating a Visual Basic SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="99147-110">Запустите среду [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (или [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="99147-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="99147-111">В меню **Файл** выберите пункт **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="99147-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="99147-112">Откроется диалоговое окно **Создание проекта** .</span><span class="sxs-lookup"><span data-stu-id="99147-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="99147-113">В диалоговом окне **типы проектов** выберите **Visual Basic**, а затем выберите **Windows**.</span><span class="sxs-lookup"><span data-stu-id="99147-113">In **Project Types** dialog box, select **Visual Basic**, and then select **Windows**.</span></span> <span data-ttu-id="99147-114">В [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] области Установленные шаблоны выберите **консольное приложение.**</span><span class="sxs-lookup"><span data-stu-id="99147-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Console Application.**</span></span>  
  
4.  <span data-ttu-id="99147-115">Используемых В поле **имя** введите имя нового приложения.</span><span class="sxs-lookup"><span data-stu-id="99147-115">(Optional) In the **Name** field, type the name of the new application.</span></span>  
  
5.  <span data-ttu-id="99147-116">Нажмите кнопку **ОК** , чтобы загрузить [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] Шаблон консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="99147-116">Click **OK** to load the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] console application template.</span></span>  
  
6.  <span data-ttu-id="99147-117">В меню **Проект** выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="99147-117">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="99147-118">Откроется диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="99147-118">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="99147-119">Нажмите кнопку **Обзор**, найдите сборки SMO в папке C:\PROGRAM Files\Microsoft SQL Server\120\SDK\Assemblies, а затем выберите следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="99147-119">Click **Browse**, locate the SMO assemblies in the C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies folder, and then select the following files.</span></span> <span data-ttu-id="99147-120">Для построения приложения SMO необходимы как минимум следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="99147-120">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="99147-121">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="99147-121">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="99147-122">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99147-122">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
     <span data-ttu-id="99147-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="99147-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="99147-124">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="99147-124">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99147-125">Используйте клавишу `Ctrl`, чтобы выбрать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="99147-125">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="99147-126">Добавьте все дополнительные сборки SMO, которые могут потребоваться.</span><span class="sxs-lookup"><span data-stu-id="99147-126">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="99147-127">Например, если программа предназначена для компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)], добавьте следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="99147-127">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="99147-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="99147-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="99147-129">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="99147-129">Click **Open**.</span></span>  
  
10. <span data-ttu-id="99147-130">В меню **вид** выберите пункт **код**.-или-выберите окно Module1. vb, чтобы отобразить окно кода.</span><span class="sxs-lookup"><span data-stu-id="99147-130">On the **View** menu, click **Code**.-Or-Select the Module1.vb window to show the code window.</span></span>  
  
11. <span data-ttu-id="99147-131">В коде перед любыми объявлениями введите следующие операторы **Imports** , чтобы определить типы в пространстве имен SMO.</span><span class="sxs-lookup"><span data-stu-id="99147-131">In the code, before any declarations, type the following **Imports** statements to qualify the types in the SMO namespace.</span></span>  
  
    ```  
    Imports Microsoft.SqlServer.Management.Smo  
    Imports Microsoft.SqlServer.Management.Common  
    ```  
  
12. <span data-ttu-id="99147-132">В SMO имеются различные пространства имен в узле Microsoft.SqlServer.Management.Smo, такие как Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="99147-132">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="99147-133">Добавьте эти пространства имен при необходимости.</span><span class="sxs-lookup"><span data-stu-id="99147-133">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="99147-134">Теперь можно добавить свой код SMO.</span><span class="sxs-lookup"><span data-stu-id="99147-134">You can now add your SMO code.</span></span>  
  
  
