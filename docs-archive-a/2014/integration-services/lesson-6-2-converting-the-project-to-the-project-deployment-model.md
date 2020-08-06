---
title: Шаг 2. Преобразование проекта в модель развертывания проекта | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7b879b2bea4afd58a48cdfc6f0890353fe6758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655821"
---
# <a name="step-2-converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="9d9f7-102">Этап 2. Преобразование проекта в модель развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="9d9f7-102">Step 2: Converting the Project to the Project Deployment Model</span></span>
  <span data-ttu-id="9d9f7-103">В этой задаче будет использоваться мастер преобразования проекта служб Integration Services для преобразования проекта в модель развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-103">In this task, you will use the Integration Services Project Conversion Wizard to convert the project to the Project Deployment Model.</span></span>  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="9d9f7-104">Преобразование проекта в модель развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="9d9f7-104">Converting the Project to the Project Deployment Model</span></span>  
  
1.  <span data-ttu-id="9d9f7-105">В меню Проект выберите пункт Преобразовать в модель развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-105">On the Project Menu, click Convert to Project Deployment Model.</span></span>  
  
2.  <span data-ttu-id="9d9f7-106">На странице "Общие сведения мастера преобразования проекта служб Integration Services" просмотрите действия, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-106">On the Integration Services Project Conversion Wizard Introduction page, review the steps then click Next.</span></span>  
  
3.  <span data-ttu-id="9d9f7-107">На странице "Выбор пакетов" в списке пакетов снимите все флажки за исключением Lesson 6.dtsx, затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-107">On the Select Packages page, in the Packages list, clear all checkboxes except Lesson 6.dtsx then click Next.</span></span>  
  
4.  <span data-ttu-id="9d9f7-108">На странице "Задание свойств проекта" нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-108">On the Specify Project Properties page, click Next.</span></span>  
  
5.  <span data-ttu-id="9d9f7-109">На странице "Задача обновления выполнения пакета" нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-109">On the Update Execute Package Task page click Next.</span></span>  
  
6.  <span data-ttu-id="9d9f7-110">На странице "Выбор конфигураций" убедитесь, что в списке конфигураций выбран пакет Lesson 6.dtsx, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-110">On the Select Configurations page, make sure the Lesson 6.dtsx package is selected in the Configurations list, then click Next.</span></span>  
  
7.  <span data-ttu-id="9d9f7-111">На странице "Параметры создания" убедитесь, что выбран пакет Lesson 6.dtsx, и область имеет значение "Пакет" в списке свойств конфигурации, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-111">On the Create Parameters page make sure the Lesson 6.dtsx package is selected, and the Scope is set to Package, in the Configuration Properties List, then Click Next.</span></span>  
  
8.  <span data-ttu-id="9d9f7-112">На странице "Параметры настройки" убедитесь, что значения для имени и значения те же имя и значение, указанные на занятии 5 для переменной и значения конфигурации, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-112">On the Configure Parameters page verify that the values for Name and Value are the same name and value specified in Lesson 5 for the variable and configuration value, then click Next.</span></span>  
  
9. <span data-ttu-id="9d9f7-113">На странице "Просмотр" панели "Сводка" обратите внимание, что мастер использовал сведения из файла конфигурации для задания свойств для преобразования.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-113">On the Review page, in the Summary pane, notice that the wizard has used the information from the configuration file to set the Properties to be converted.</span></span>  
  
10. <span data-ttu-id="9d9f7-114">Щелкните Преобразовать.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-114">Click Convert.</span></span>  
  
     <span data-ttu-id="9d9f7-115">После завершения преобразования отображается сообщение, предупреждающее, что изменения не сохраняются до сохранения проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-115">When the conversion completes a message is displayed warning that the changes are not saved until the project is saved in Visual Studio.</span></span> <span data-ttu-id="9d9f7-116">В диалоговом окне предупреждения нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-116">Click OK on the warning dialog.</span></span>  
  
11. <span data-ttu-id="9d9f7-117">В мастере преобразования проекта служб Integration Services нажмите кнопку "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="9d9f7-117">On the Integration Services Project Conversion Wizard click Close.</span></span>  
  
12. <span data-ttu-id="9d9f7-118">В SQL Server Data Tools щелкните меню "Файл", а затем нажмите кнопку "Сохранить", чтобы сохранить преобразованный пакет.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-118">In SQL Server Data Tools, click the File menu, then click Save to save the converted package.</span></span>  
  
13. <span data-ttu-id="9d9f7-119">Перейдите на вкладку "Параметры" и убедитесь, что пакет теперь содержит параметр для VarFolderName и, что значение является тем же путем, который был определен для папки New Sample Data из файла конфигурации занятия 5.</span><span class="sxs-lookup"><span data-stu-id="9d9f7-119">Click the Parameters Tab and verify that the package now contains a parameter for VarFolderName and that the value is the same path specified for the New Sample Data folder from the Lesson 5 configuration file.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9d9f7-120">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="9d9f7-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9d9f7-121">Шаг 3. Проверка пакета, созданного на занятии 6</span><span class="sxs-lookup"><span data-stu-id="9d9f7-121">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
  
