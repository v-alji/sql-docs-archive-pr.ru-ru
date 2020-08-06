---
title: Связывание расширения файла с редактором кода
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- file extensions [SQL Server]
- associating file extensions [SQL Server]
- Query Editor [SQL Server Management Studio], associating file extensions
ms.assetid: 193630f4-93de-4950-8f36-68702531f925
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e8cfbc89892a99971e985ffd3ff10b99f89fe53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658178"
---
# <a name="associate-file-extensions-to-a-code-editor"></a><span data-ttu-id="fcfc4-102">Связывание расширения файла с редактором кода</span><span class="sxs-lookup"><span data-stu-id="fcfc4-102">Associate File Extensions to a Code Editor</span></span>
  <span data-ttu-id="fcfc4-103">Связь расширений файлов с конкретным редактором кода позволяет открывать файл соответствующим редактором кода среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] двойным щелчком файла в проводнике Windows.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-103">Associating file extensions to a specific code editor allows you to open a file with the appropriate [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] code editor when you double-click a file in Windows Explorer.</span></span> <span data-ttu-id="fcfc4-104">Расширения, обычно используемые средой [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], такие как SQL и MDX, задаются во время установки.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-104">The extensions commonly used by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation.</span></span> <span data-ttu-id="fcfc4-105">Новые расширения файлов должны быть связаны со средой [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-105">New file extensions must also be associated to [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in the file system.</span></span> <span data-ttu-id="fcfc4-106">Эту возможность можно использовать для открытия файлов, созданных в других редакторах, или для открытия переименованных файлов, таких как резервные копии SQL-файлов, переименованных в файлы с расширением BAK.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-106">You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.</span></span>  
  
 <span data-ttu-id="fcfc4-107">Этот процесс включает два шага.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-107">There are two steps in the process.</span></span> <span data-ttu-id="fcfc4-108">Вначале нужно связать расширение со средой [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], а затем — с конкретным редактором кода.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-108">First associate the extension with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-sql-server-management-studio"></a><span data-ttu-id="fcfc4-109">Связывание нового расширения файла со средой SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fcfc4-109">To associate a new file extension with SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="fcfc4-110">В меню **Пуск** последовательно укажите **Все программы**, **Стандартные**, **Проводник**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="fcfc4-111">В проводнике Windows в меню **Сервис** выберите **Свойства папки**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-111">In Windows Explorer, on the **Tools** menu, click **Folder Options**.</span></span>  
  
3.  <span data-ttu-id="fcfc4-112">В диалоговом окне **Свойства папки** на вкладке **Типы файлов** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-112">In the **Folder Options** dialog box, on the **File Types** tab, click **New**.</span></span>  
  
4.  <span data-ttu-id="fcfc4-113">В диалоговом окне **Создание нового расширения** в поле **Расширение** введите новое расширение файла, которое нужно задать, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-113">In the **Create New Extension** dialog box, in the **File Extension** box, type the new file extension that you want to associate, and then click **OK**.</span></span> <span data-ttu-id="fcfc4-114">Не ставьте перед расширением точку.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-114">Do not start the extension with a period.</span></span>  
  
5.  <span data-ttu-id="fcfc4-115">В списке **Зарегистрированные типы файлов** выберите новое расширение и нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-115">In the **Registered file** types box, click on your new extension, and then click **Change**.</span></span>  
  
6.  <span data-ttu-id="fcfc4-116">В диалоговом окне **Открыть с помощью** выберите пункт **SSMS — среда SQL Server Management Studio** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-116">In the **Open With** dialog box, click **SSMS - SQL Server Management Studio**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="fcfc4-117">Нажмите **Закрыть** , чтобы закрыть диалоговое окно **Свойства папки** , и закройте проводник Windows.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-117">Click **Close** to close the **Folder Options** dialog box, and then close Windows Explorer.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-a-code-editor-in-sql-server-management-studio"></a><span data-ttu-id="fcfc4-118">Связывание нового расширения файла с редактором кода в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fcfc4-118">To associate a new file extension with a code editor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="fcfc4-119">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Сервис** выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="fcfc4-120">В диалоговом окне **Параметры** щелкните **Текстовый редактор**, а затем — **Расширение файла**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-120">In the **Options** dialog box, click **Text Editor**, and then click **File Extension**.</span></span>  
  
3.  <span data-ttu-id="fcfc4-121">В поле **Расширение** введите новое расширение файла.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-121">In the **Extension** box, type your new file extension.</span></span>  
  
4.  <span data-ttu-id="fcfc4-122">В поле **Редактор** выберите редактор кода, который хотите использовать для открытия данного типа файлов, нажмите кнопку **Добавить**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fcfc4-122">In the **Editor** box, click the code editor that you wish to use to open this file type, click **Add**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcfc4-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcfc4-123">See Also</span></span>  
 [<span data-ttu-id="fcfc4-124">Программа SSMS</span><span class="sxs-lookup"><span data-stu-id="fcfc4-124">Ssms Utility</span></span>](../../ssms/ssms-utility.md)  
  
  
