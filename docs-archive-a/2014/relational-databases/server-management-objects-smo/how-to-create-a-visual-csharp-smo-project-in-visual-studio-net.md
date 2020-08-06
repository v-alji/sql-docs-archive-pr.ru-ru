---
title: Создание проекта SMO в Visual C# в Visual Studio .NET | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
author: stevestein
ms.author: sstein
ms.openlocfilehash: b78820fafd37675332e6703cabbb87e78bde5864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665983"
---
# <a name="create-a-visual-c-smo-project-in-visual-studio-net"></a><span data-ttu-id="0410a-102">создание проекта SMO на языке Visual C# в среде Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="0410a-102">Create a Visual C# SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="0410a-103">В данном разделе описывается, как построить простое консольное приложение командной строки SMO.</span><span class="sxs-lookup"><span data-stu-id="0410a-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="0410a-104">В этом примере импортируются пространства имен, что позволяет программе ссылаться на типы объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="0410a-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="0410a-105">Импорт пространства имен `Agent` необязателен.</span><span class="sxs-lookup"><span data-stu-id="0410a-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="0410a-106">Его следует выполнить при написании программы, в которой используется агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0410a-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="0410a-107">Пространство имен `Common` требуется для установления безопасного соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0410a-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0410a-108">Пространство имен `SqlClient` используется для обработки ошибок, связанных с исключениями SQL.</span><span class="sxs-lookup"><span data-stu-id="0410a-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a><span data-ttu-id="0410a-109">Создание проекта SMO на языке Visual C# в среде Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="0410a-109">Creating a Visual C# SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="0410a-110">Запустите среду [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (или [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0410a-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="0410a-111">В меню **Файл** выберите пункт **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="0410a-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="0410a-112">Откроется диалоговое окно **Создание проекта** .</span><span class="sxs-lookup"><span data-stu-id="0410a-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="0410a-113">В диалоговом окне **типы проектов** выберите **Visual C#**, а затем выберите **Windows**.</span><span class="sxs-lookup"><span data-stu-id="0410a-113">In **Project Types** dialog box, select **Visual C#**, and then select **Windows**.</span></span> <span data-ttu-id="0410a-114">В [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] области Установленные шаблоны выберите **приложение Windows**.</span><span class="sxs-lookup"><span data-stu-id="0410a-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Windows Application**.</span></span>  
  
4.  <span data-ttu-id="0410a-115">Используемых В поле **имя** введите имя нового приложения.</span><span class="sxs-lookup"><span data-stu-id="0410a-115">(Optional) In the **Name** field, type the name of the new application</span></span>  
  
5.  <span data-ttu-id="0410a-116">Выберите тип приложения Visual C#.</span><span class="sxs-lookup"><span data-stu-id="0410a-116">Select the Visual C# application type.</span></span> <span data-ttu-id="0410a-117">Для приведенных ниже примеров выберите **консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="0410a-117">For the examples that follow, select **Console Application**.</span></span>  
  
6.  <span data-ttu-id="0410a-118">В меню **Проект** выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="0410a-118">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="0410a-119">Откроется диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="0410a-119">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="0410a-120">Нажмите кнопку **Обзор**, найдите сборки SMO в [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] папке, а затем выберите следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="0410a-120">Click **Browse**, locate the SMO assemblies in the [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] folder, and then select the following files.</span></span> <span data-ttu-id="0410a-121">Для построения приложения SMO необходимы как минимум следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="0410a-121">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="0410a-122">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="0410a-122">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="0410a-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="0410a-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="0410a-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="0410a-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
     <span data-ttu-id="0410a-125">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="0410a-125">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0410a-126">Используйте клавишу `Ctrl`, чтобы выбрать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="0410a-126">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="0410a-127">Добавьте все дополнительные сборки SMO, которые могут потребоваться.</span><span class="sxs-lookup"><span data-stu-id="0410a-127">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="0410a-128">Например, если программа предназначена для компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)], добавьте следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="0410a-128">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="0410a-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="0410a-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="0410a-130">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="0410a-130">Click **Open**.</span></span>  
  
10. <span data-ttu-id="0410a-131">В меню **вид** выберите пункт **код**.-или-выберите PROGRAM1.cs [Design] Windows и дважды щелкните Windows Form, чтобы открыть окно кода.</span><span class="sxs-lookup"><span data-stu-id="0410a-131">On the **View** menu, click **Code**.-Or-Select the Program1.cs [Design] Windows and double-click the windows form to show the code window.</span></span>  
  
11. <span data-ttu-id="0410a-132">В коде перед инструкцией пространства имен введите следующие инструкции `using` для определения типов в пространстве имен объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="0410a-132">In the code, before the namespace statement, type the following `using` statements to qualify the types in the SMO namespace:</span></span>  
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
12. <span data-ttu-id="0410a-133">В SMO имеются различные пространства имен в узле Microsoft.SqlServer.Management.Smo, такие как Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="0410a-133">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="0410a-134">Добавьте эти пространства имен при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0410a-134">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="0410a-135">Теперь можно добавить свой код SMO.</span><span class="sxs-lookup"><span data-stu-id="0410a-135">You can now add your SMO code.</span></span>  
  
  
