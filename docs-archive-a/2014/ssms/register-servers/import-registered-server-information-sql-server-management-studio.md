---
title: Импорт сведений о зарегистрированном сервере
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.importregisteredservers.f1
helpviewer_keywords:
- transferring registered server information
- Registered Servers [SQL Server], importing
- importing registered server information
ms.assetid: cc497a14-1360-4887-b70c-002f042823b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f2eddb3b83f73253e977316767f2b930bc8ab9ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737403"
---
# <a name="import-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="6b78c-102">Импорт сведений о зарегистрированном сервере (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6b78c-102">Import Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6b78c-103">В этом разделе описывается, как импортировать сохраненные сведения о зарегистрированных серверах в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b78c-103">This topic describes how to import saved registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="6b78c-104">Экспорт и импорт файлов зарегистрированных серверов позволяет легко настроить для нескольких компьютеров одинаковые зарегистрированные серверы.</span><span class="sxs-lookup"><span data-stu-id="6b78c-104">Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="6b78c-105">Это удобно при управлении большим количеством серверов с компьютеров, расположенных в различных местах, или если требуется сконфигурировать базовые настройки соединения для менее опытных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6b78c-105">This is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less-experienced user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b78c-106">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] нельзя импортировать сведения о зарегистрированных серверах из более ранних версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b78c-106">You cannot import registered server information into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-import-registered-server-information"></a><span data-ttu-id="6b78c-107">Импорт сведений о зарегистрированных серверах</span><span class="sxs-lookup"><span data-stu-id="6b78c-107">To import registered server information</span></span>  
  
1.  <span data-ttu-id="6b78c-108">В окне «Зарегистрированные серверы» выберите обозначение типа сервера на панели инструментов зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="6b78c-108">In Registered Servers, click the server type on the Registered Servers toolbar.</span></span> <span data-ttu-id="6b78c-109">Тип сервера должен совпадать с типом экспортированного файла зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="6b78c-109">The server type must be the same as the registered server export file type.</span></span> <span data-ttu-id="6b78c-110">Например, если экспортированы сведения о зарегистрированном сервере [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , следует выбрать в области «Зарегистрированные серверы» вариант **SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="6b78c-110">For example, if you have exported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registered server information, you must click **SQL Server** on the Registered Servers toolbar.</span></span>  
  
2.  <span data-ttu-id="6b78c-111">Щелкните правой кнопкой мыши группу серверов и выберите **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="6b78c-111">Right-click a server group, and select **Import**.</span></span>  
  
3.  <span data-ttu-id="6b78c-112">В диалоговом окне **Импорт данных о зарегистрированных серверах** выберите зарегистрированные серверы, которые нужно импортировать, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b78c-112">In the **Import Registered Servers** dialog box, select the registered servers file to import, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6b78c-113">**Файл импорта**</span><span class="sxs-lookup"><span data-stu-id="6b78c-113">**Import file**</span></span>  
     <span data-ttu-id="6b78c-114">Введите в текстовое поле имя файла импорта или нажмите кнопку обзора ( **...** ), чтобы найти файл импорта на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="6b78c-114">Type the name of the import file in the text box, or click the Browse button (**...**) to locate the import file on the client computer.</span></span> <span data-ttu-id="6b78c-115">Если выбрать существующий файл, то сведения о зарегистрированном сервере добавятся в этот файл.</span><span class="sxs-lookup"><span data-stu-id="6b78c-115">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="6b78c-116">Файлом импорта может быть только ранее экспортированный файл зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="6b78c-116">The import file can only be a previously exported registered server file.</span></span> <span data-ttu-id="6b78c-117">Файлы зарегистрированных серверов имеют расширение REGSVR.</span><span class="sxs-lookup"><span data-stu-id="6b78c-117">Registered server files have a .regsrvr extension.</span></span>  
  
     <span data-ttu-id="6b78c-118">**Выберите группу серверов для импорта**</span><span class="sxs-lookup"><span data-stu-id="6b78c-118">**Select the server group to import to**</span></span>  
     <span data-ttu-id="6b78c-119">Выберите корневой узел дерева или отдельную группу серверов, в которую будут импортированы зарегистрированные серверы.</span><span class="sxs-lookup"><span data-stu-id="6b78c-119">Select the root node or a particular server group to which the registered server entries in the file will be imported.</span></span> <span data-ttu-id="6b78c-120">Можно импортировать в файл экспорта все зарегистрированные серверы, зарегистрированные серверы в определенной группе серверов или отдельные зарегистрированные серверы.</span><span class="sxs-lookup"><span data-stu-id="6b78c-120">You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="6b78c-121">Возможность импорта является рекурсивной. Например, если группа серверов А содержит группу серверов В, а группа серверов В содержит группы C и D, то при импорте группы А импортируются все серверы из групп А, В, С и D.</span><span class="sxs-lookup"><span data-stu-id="6b78c-121">The import functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, importing server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="6b78c-122">Группа серверов отображает только группы серверов из дерева текущего зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="6b78c-122">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="6b78c-123">Если выбран импорт существующей группы серверов или сервера, выдается запрос на подтверждение перезаписи существующего сервера или группы серверов.</span><span class="sxs-lookup"><span data-stu-id="6b78c-123">If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.</span></span>  
  
 <span data-ttu-id="6b78c-124">Регистрации серверов, использующие метод проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , хранят пароли отдельно для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="6b78c-124">Server registrations that use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="6b78c-125">После импорта регистраций серверов пользователи должны ввести пароль при первом подключении к каждому серверу, сохраняя пароли в списке зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="6b78c-125">After importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="6b78c-126">Если серверы зарегистрированы с помощью проверки подлинности Windows, нет необходимости использовать эту операцию.</span><span class="sxs-lookup"><span data-stu-id="6b78c-126">This is not necessary for servers registered through Windows Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b78c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b78c-127">See Also</span></span>  
 <span data-ttu-id="6b78c-128">[Изменение &#40;регистрации сервера SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Экспорт сведений о зарегистрированных серверах &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6b78c-128">[Change a Server's Registration &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Export Registered Server Information &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="6b78c-129">Создание нового зарегистрированного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6b78c-129">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)  
  
  
