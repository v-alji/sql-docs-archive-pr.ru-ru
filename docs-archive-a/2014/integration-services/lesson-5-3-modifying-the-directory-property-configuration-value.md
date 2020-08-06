---
title: Шаг 3. Изменение значения конфигурации свойства Directory | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a71a7a181322d60caca98da4ddf3261cbce99c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657147"
---
# <a name="step-3-modifying-the-directory-property-configuration-value"></a><span data-ttu-id="34a8c-102">Шаг 3. Изменение значения конфигурации свойства Directory</span><span class="sxs-lookup"><span data-stu-id="34a8c-102">Step 3: Modifying the Directory Property Configuration Value</span></span>
  <span data-ttu-id="34a8c-103">В этой задаче предстоит изменить хранимый в файле SSISTutorial.dtsConfig параметр настройки свойства Value переменной уровня пакета `User::varFolderName`.</span><span class="sxs-lookup"><span data-stu-id="34a8c-103">In this task, you will modify the configuration setting, stored in the SSISTutorial.dtsConfig file, for the Value property of the package-level variable `User::varFolderName`.</span></span> <span data-ttu-id="34a8c-104">Эта переменная обновляет свойство Directory контейнера "цикл по каждому элементу".</span><span class="sxs-lookup"><span data-stu-id="34a8c-104">The variable updates the Directory property of the Foreach Loop container.</span></span> <span data-ttu-id="34a8c-105">Измененное значение будет указывать на `New Sample Data` папку, созданную в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="34a8c-105">The modified value will point to the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="34a8c-106">После изменения параметра настройки конфигурации и выполнения пакета свойство Directory будет обновляться этой переменной с использованием значения из файла конфигурации, а не значения из каталога, первоначально заданного в данном пакете.</span><span class="sxs-lookup"><span data-stu-id="34a8c-106">After you modify the configuration setting and run the package, the Directory property will be updated by the variable, using the value populated from the configuration file instead of the directory value originally configured in the package.</span></span>  
  
### <a name="to-modify-the-configuration-setting-of-the-directory-property"></a><span data-ttu-id="34a8c-107">Изменение параметра конфигурации для свойства Directory</span><span class="sxs-lookup"><span data-stu-id="34a8c-107">To modify the configuration setting of the Directory property</span></span>  
  
1.  <span data-ttu-id="34a8c-108">В приложении «Блокнот» или другом текстовом редакторе найдите и откройте файл конфигурации SSISTutorial.dtsConfig, созданный в предыдущей задаче с помощью мастера настройки пакета.</span><span class="sxs-lookup"><span data-stu-id="34a8c-108">In Notepad or any other text editor, locate and open the SSISTutorial.dtsConfig configuration file that you created by using the Package Configuration Wizard in the previous task.</span></span>  
  
2.  <span data-ttu-id="34a8c-109">Измените значение элемента **ConfiguredValue пуст** , чтобы оно совпадало с путем к `New Sample Data` папке, созданной в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="34a8c-109">Change the value of the **ConfiguredValue** element to match the path of the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="34a8c-110">Не заключайте этот путь в кавычки.</span><span class="sxs-lookup"><span data-stu-id="34a8c-110">Do not surround the path in quotes.</span></span> <span data-ttu-id="34a8c-111">Если `New Sample Data` Папка находится на корневом уровне диска (например, C: \\ ), обновленный код XML должен быть подобен следующему примеру:</span><span class="sxs-lookup"><span data-stu-id="34a8c-111">If the `New Sample Data` folder is at the root level of your drive (for example, C:\\), the updated XML should be similar to the following sample:</span></span>  
  
     `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
     <span data-ttu-id="34a8c-112">Разумеется, сведения о заголовке,, `GeneratedBy` `GeneratedFromPackageID` и **женератеддате** будут отличаться в файле.</span><span class="sxs-lookup"><span data-stu-id="34a8c-112">The heading information, `GeneratedBy`, `GeneratedFromPackageID`, and **GeneratedDate** will be different in your file, of course.</span></span> <span data-ttu-id="34a8c-113">`Configuration` — элемент, на который необходимо обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="34a8c-113">The element to note is the `Configuration` element.</span></span> <span data-ttu-id="34a8c-114">Свойство `Value` переменной `User::varFolderName` теперь содержит значение «C:\New Sample Data».</span><span class="sxs-lookup"><span data-stu-id="34a8c-114">The `Value` property of the variable, `User::varFolderName`, now contains C:\New Sample Data.</span></span>  
  
3.  <span data-ttu-id="34a8c-115">Сохраните изменения и закройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="34a8c-115">Save the change, and then close the text editor.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="34a8c-116">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="34a8c-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="34a8c-117">Шаг 4. Проверка учебного пакета, созданного на занятии 5</span><span class="sxs-lookup"><span data-stu-id="34a8c-117">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](../integration-services/lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
  
